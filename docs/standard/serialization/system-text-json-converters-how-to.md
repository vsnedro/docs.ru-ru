---
title: Как написать настраиваемые преобразователи для сериализации JSON — .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: e0b769d7bb6b336d226cd48de1932524c4d7e74d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811071"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="89108-102">Как написать настраиваемые преобразователи для сериализации JSON (маршалинг) в .NET</span><span class="sxs-lookup"><span data-stu-id="89108-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="89108-103">В этой статье показано, как создать настраиваемые преобразователи для классов сериализации JSON, предоставляемых в пространстве имен <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="89108-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="89108-104">Общие сведения о `System.Text.Json` см. в статье [Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="89108-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="89108-105">*Преобразователь* — это класс, который преобразует объект или значение в формат JSON и обратно.</span><span class="sxs-lookup"><span data-stu-id="89108-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="89108-106">Пространство имен `System.Text.Json` содержит встроенные преобразователи для большинства примитивных типов, которые сопоставляются с примитивами JavaScript.</span><span class="sxs-lookup"><span data-stu-id="89108-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="89108-107">Вы можете создавать настраиваемые преобразователи для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="89108-107">You can write custom converters:</span></span>

* <span data-ttu-id="89108-108">Чтобы переопределить поведение встроенного преобразователя, используемое по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89108-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="89108-109">Например, может потребоваться, чтобы значения `DateTime` были представлены в формате дд.мм.гггг вместо формата ISO 8601-1:2019 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89108-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="89108-110">Для поддержки настраиваемого типа значения.</span><span class="sxs-lookup"><span data-stu-id="89108-110">To support a custom value type.</span></span> <span data-ttu-id="89108-111">Например, структуры `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="89108-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="89108-112">Вы также можете создать настраиваемые преобразователи для настройки или расширения `System.Text.Json` с функциональностью, не входящей в текущий выпуск.</span><span class="sxs-lookup"><span data-stu-id="89108-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="89108-113">Далее в этой статье описываются следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="89108-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="89108-114">[Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="89108-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="89108-115">[Поддержка словаря с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="89108-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="89108-116">[Поддержка полиморфной десериализации](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="89108-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="89108-117">[Поддержка кругового пути для Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="89108-117">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="89108-118">Шаблоны настраиваемых преобразователей</span><span class="sxs-lookup"><span data-stu-id="89108-118">Custom converter patterns</span></span>

<span data-ttu-id="89108-119">Существует два шаблона для создания настраиваемого преобразователя: базовый шаблон и шаблон фабрики.</span><span class="sxs-lookup"><span data-stu-id="89108-119">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="89108-120">Шаблон фабрики предназначен для преобразователей, обрабатывающих типы `Enum` или открытые универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="89108-120">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="89108-121">Базовый шаблон предназначен для неуниверсальных и закрытых универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="89108-121">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="89108-122">Например, для преобразователей следующих типов требуется шаблон фабрики:</span><span class="sxs-lookup"><span data-stu-id="89108-122">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="89108-123">Ниже приведены некоторые примеры типов, которые могут быть обработаны базовым шаблоном:</span><span class="sxs-lookup"><span data-stu-id="89108-123">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="89108-124">Базовый шаблон создает класс, который может работать с одним типом.</span><span class="sxs-lookup"><span data-stu-id="89108-124">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="89108-125">Шаблон фабрики создает класс, который в среде выполнения определяет, какой конкретный тип требуется, и динамически создает соответствующий преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-125">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="89108-126">Пример базового преобразователя</span><span class="sxs-lookup"><span data-stu-id="89108-126">Sample basic converter</span></span>

<span data-ttu-id="89108-127">Следующий пример представляет собой преобразователь, который переопределяет сериализацию по умолчанию для существующего типа данных.</span><span class="sxs-lookup"><span data-stu-id="89108-127">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="89108-128">Для свойств `DateTimeOffset` преобразователь использует формат дд.мм.гггг.</span><span class="sxs-lookup"><span data-stu-id="89108-128">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="89108-129">Пример преобразователя шаблона фабрики</span><span class="sxs-lookup"><span data-stu-id="89108-129">Sample factory pattern converter</span></span>

<span data-ttu-id="89108-130">В следующем примере кода показан настраиваемый преобразователь, который работает с `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="89108-130">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="89108-131">Код соответствует шаблону фабрики, так как первый параметр универсального типа является `Enum`, а второй — открытым.</span><span class="sxs-lookup"><span data-stu-id="89108-131">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="89108-132">Метод `CanConvert` возвращает `true` только для `Dictionary` с двумя универсальными параметрами, первый из которых является типом `Enum`.</span><span class="sxs-lookup"><span data-stu-id="89108-132">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="89108-133">Внутренний преобразователь получает существующий преобразователь для работы с любым типом, предоставленным во время выполнения для `TValue`.</span><span class="sxs-lookup"><span data-stu-id="89108-133">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="89108-134">Предыдущий код аналогичен тому, который приведен в разделе [Поддержка словаря с ключом, не являющимся строкой](#support-dictionary-with-non-string-key) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="89108-134">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="89108-135">Инструкции по базовому шаблону</span><span class="sxs-lookup"><span data-stu-id="89108-135">Steps to follow the basic pattern</span></span>

<span data-ttu-id="89108-136">Ниже описывается, как создать преобразователь с помощью базового шаблона:</span><span class="sxs-lookup"><span data-stu-id="89108-136">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="89108-137">Создайте класс, производный от <xref:System.Text.Json.Serialization.JsonConverter%601>, где `T` — это тип для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="89108-137">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="89108-138">Переопределите метод `Read`, чтобы десериализировать входящие данные JSON и преобразовать их в тип `T`.</span><span class="sxs-lookup"><span data-stu-id="89108-138">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="89108-139">Для чтения JSON используйте передаваемое в метод значение <xref:System.Text.Json.Utf8JsonReader>.</span><span class="sxs-lookup"><span data-stu-id="89108-139">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="89108-140">Переопределите метод `Write` для сериализации входящего объекта типа `T`.</span><span class="sxs-lookup"><span data-stu-id="89108-140">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="89108-141">Для записи JSON используйте передаваемое в метод значение <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="89108-141">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="89108-142">Переопределяйте метод `CanConvert` только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="89108-142">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="89108-143">Реализация по умолчанию возвращает `true`, если тип для преобразования имеет тип `T`.</span><span class="sxs-lookup"><span data-stu-id="89108-143">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="89108-144">Поэтому для преобразователей, поддерживающих только тип `T`, не требуется переопределять этот метод.</span><span class="sxs-lookup"><span data-stu-id="89108-144">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="89108-145">Пример преобразователя, в котором требуется переопределить этот метод, см. в разделе [Поддержка полиморфной десериализации](#support-polymorphic-deserialization) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="89108-145">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="89108-146">Вы можете ссылаться на [исходный код встроенных преобразователей](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) в качестве эталонных реализаций для написания настраиваемых преобразователей.</span><span class="sxs-lookup"><span data-stu-id="89108-146">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="89108-147">Инструкции по шаблону фабрики</span><span class="sxs-lookup"><span data-stu-id="89108-147">Steps to follow the factory pattern</span></span>

<span data-ttu-id="89108-148">Ниже описывается, как создать преобразователь с помощью шаблона фабрики:</span><span class="sxs-lookup"><span data-stu-id="89108-148">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="89108-149">Создайте класс, наследующий от класса <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="89108-149">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="89108-150">Переопределите метод `CanConvert`, чтобы он возвращал значение true, если преобразователь может обрабатывать этот тип.</span><span class="sxs-lookup"><span data-stu-id="89108-150">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="89108-151">Например, если преобразователь предназначен для `List<T>`, он может обрабатывать только `List<int>`, `List<string>` и `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="89108-151">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="89108-152">Переопределите метод `CreateConverter`, чтобы он возвращал экземпляр класса преобразователя, обрабатывающего тип для преобразования, который будет предоставлен во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="89108-152">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="89108-153">Создайте класс преобразователя с помощью метода `CreateConverter`.</span><span class="sxs-lookup"><span data-stu-id="89108-153">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="89108-154">Шаблон фабрики необходим для открытых универсальных шаблонов, так как код для преобразования объекта в строку и обратно не совпадает для всех типов.</span><span class="sxs-lookup"><span data-stu-id="89108-154">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="89108-155">Преобразователь для открытого универсального типа (например, `List<T>`) должен создать преобразователь для закрытого универсального типа (например, `List<DateTime>`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="89108-155">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="89108-156">Необходимо написать код для обработки каждого закрытого универсального типа, который может обрабатывать преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-156">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="89108-157">Тип `Enum` похож на открытый универсальный тип: преобразователь для `Enum` должен создать преобразователь для определенного типа `Enum` (например, `WeekdaysEnum`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="89108-157">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="89108-158">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="89108-158">Error handling</span></span>

<span data-ttu-id="89108-159">Если необходимо вызвать исключение в коде обработки ошибок, рассмотрите возможность создания <xref:System.Text.Json.JsonException> без сообщения.</span><span class="sxs-lookup"><span data-stu-id="89108-159">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="89108-160">Этот тип исключения автоматически создает сообщение, содержащее путь к части JSON, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="89108-160">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="89108-161">Например, инструкция `throw new JsonException();` выдает сообщение об ошибке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="89108-161">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="89108-162">Если вы предоставляете сообщение (например, `throw new JsonException("Error occurred")`), исключение по-прежнему предоставляет путь в свойстве <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="89108-162">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="89108-163">Регистрация настраиваемого преобразователя</span><span class="sxs-lookup"><span data-stu-id="89108-163">Register a custom converter</span></span>

<span data-ttu-id="89108-164">*Зарегистрируйте* настраиваемый преобразователь, чтобы использовать методы `Serialize` и `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="89108-164">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="89108-165">Воспользуйтесь одним из перечисленных ниже подходов.</span><span class="sxs-lookup"><span data-stu-id="89108-165">Choose one of the following approaches:</span></span>

* <span data-ttu-id="89108-166">Добавьте экземпляр класса преобразователя в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89108-166">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="89108-167">Примените атрибут [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к свойствам, для которых требуется настраиваемый преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="89108-168">Примените атрибут [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к классу или структуре, представляющей настраиваемый тип значения.</span><span class="sxs-lookup"><span data-stu-id="89108-168">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="89108-169">Пример регистрации — коллекция преобразователей</span><span class="sxs-lookup"><span data-stu-id="89108-169">Registration sample - Converters collection</span></span>

<span data-ttu-id="89108-170">Ниже приведен пример, который делает <xref:System.ComponentModel.DateTimeOffsetConverter> классом по умолчанию для свойств типа <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="89108-170">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="89108-171">Предположим, что вы сериализуете экземпляр следующего типа.</span><span class="sxs-lookup"><span data-stu-id="89108-171">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="89108-172">Ниже приведен пример выходных данных JSON, в котором показано использование настраиваемого преобразователя.</span><span class="sxs-lookup"><span data-stu-id="89108-172">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="89108-173">Следующий код использует тот же подход для десериализации с помощью настраиваемого преобразователя `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="89108-173">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="89108-174">Пример регистрации — [JsonConverter] для свойства</span><span class="sxs-lookup"><span data-stu-id="89108-174">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="89108-175">В следующем примере кода выбирается настраиваемый преобразователь для свойства `Date`.</span><span class="sxs-lookup"><span data-stu-id="89108-175">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="89108-176">В коде для сериализации `WeatherForecastWithConverterAttribute` не нужно использовать `JsonSerializeOptions.Converters`.</span><span class="sxs-lookup"><span data-stu-id="89108-176">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="89108-177">В коде для десериализации также не нужно использовать `Converters`.</span><span class="sxs-lookup"><span data-stu-id="89108-177">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="89108-178">Пример регистрации — [JsonConverter] для типа</span><span class="sxs-lookup"><span data-stu-id="89108-178">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="89108-179">Ниже приведен код, создающий структуру и применяющий к ней атрибут `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="89108-179">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Temperature.cs)]

<span data-ttu-id="89108-180">Ниже приведен настраиваемый преобразователь для предыдущей структуры.</span><span class="sxs-lookup"><span data-stu-id="89108-180">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/TemperatureConverter.cs)]

<span data-ttu-id="89108-181">Атрибут `[JsonConvert]` в структуре регистрирует настраиваемый преобразователь в качестве значения по умолчанию для свойств типа `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="89108-181">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="89108-182">Этот преобразователь автоматически используется в свойстве `TemperatureCelsius` следующего типа при его сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="89108-182">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="89108-183">Очередность регистрации преобразователей</span><span class="sxs-lookup"><span data-stu-id="89108-183">Converter registration precedence</span></span>

<span data-ttu-id="89108-184">Во время сериализации или десериализации выбирается преобразователь для каждого элемента JSON в следующем порядке — от наивысшего приоритета к наименьшему.</span><span class="sxs-lookup"><span data-stu-id="89108-184">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="89108-185">Атрибут `[JsonConverter]` применяется к свойству.</span><span class="sxs-lookup"><span data-stu-id="89108-185">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="89108-186">Преобразователь, добавляемый в коллекцию `Converters`.</span><span class="sxs-lookup"><span data-stu-id="89108-186">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="89108-187">Атрибут `[JsonConverter]` применяется к настраиваемому типу значения или POCO.</span><span class="sxs-lookup"><span data-stu-id="89108-187">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="89108-188">Если в коллекции `Converters` зарегистрировано несколько настраиваемых преобразователей для типов, то используется первый преобразователь, возвращающий значение true для `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="89108-188">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="89108-189">Встроенный преобразователь выбирается только в том случае, если соответствующий настраиваемый преобразователь не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="89108-189">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="89108-190">Примеры преобразователей для выполнения стандартных сценариев</span><span class="sxs-lookup"><span data-stu-id="89108-190">Converter samples for common scenarios</span></span>

<span data-ttu-id="89108-191">В следующих разделах приведены примеры преобразователей, в которых рассматриваются распространенные сценарии, необрабатываемые встроенными функциями.</span><span class="sxs-lookup"><span data-stu-id="89108-191">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* <span data-ttu-id="89108-192">[Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="89108-192">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties)</span></span>
* <span data-ttu-id="89108-193">[Поддержка словаря с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="89108-193">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key)</span></span>
* <span data-ttu-id="89108-194">[Поддержка полиморфной десериализации](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="89108-194">[Support polymorphic deserialization](#support-polymorphic-deserialization)</span></span>
* <span data-ttu-id="89108-195">[Поддержка кругового пути для Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="89108-195">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="89108-196">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="89108-196">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="89108-197">При десериализации в свойство типа `object` создается объект `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="89108-197">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="89108-198">Причина заключается в том, что десериализатор не знает, какой тип среды выполнения создать, и не пытается угадать.</span><span class="sxs-lookup"><span data-stu-id="89108-198">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="89108-199">Например, если свойство JSON имеет значение true, десериализатор не определит, что значение является `Boolean`, а если у элемента есть значение 01/01/2019, десериализатор не определит, что это `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="89108-199">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="89108-200">Определение типа может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="89108-200">Type inference can be inaccurate.</span></span> <span data-ttu-id="89108-201">Если десериализатор анализирует число JSON, не имеющее десятичного разделителя в качестве `long`, это может привести к проблемам в виде выхода за пределы диапазона, если значение первоначально было сериализовано как `ulong` или `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="89108-201">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="89108-202">Анализ числа с десятичным разделителем в качестве `double` может привести к потере точности, если это число было первоначально сериализовано как `decimal`.</span><span class="sxs-lookup"><span data-stu-id="89108-202">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="89108-203">В следующем коде показан настраиваемый преобразователь для свойств `object` сценариев с определением типа.</span><span class="sxs-lookup"><span data-stu-id="89108-203">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="89108-204">Код преобразует:</span><span class="sxs-lookup"><span data-stu-id="89108-204">The code converts:</span></span>

* <span data-ttu-id="89108-205">`true` и `false` в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="89108-205">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="89108-206">Числа без десятичного числа в `long`.</span><span class="sxs-lookup"><span data-stu-id="89108-206">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="89108-207">Числа с десятичным числом в `double`.</span><span class="sxs-lookup"><span data-stu-id="89108-207">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="89108-208">Даты в `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="89108-208">Dates to `DateTime`</span></span>
* <span data-ttu-id="89108-209">Строки в `string`.</span><span class="sxs-lookup"><span data-stu-id="89108-209">Strings to `string`</span></span>
* <span data-ttu-id="89108-210">Все остальное в `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="89108-210">Everything else to `JsonElement`</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="89108-211">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-211">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="89108-212">Ниже приведен пример типа со свойствами `object`.</span><span class="sxs-lookup"><span data-stu-id="89108-212">Here's an example type with `object` properties:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="89108-213">Следующий пример JSON для десериализации содержит значения, которые будут десериализованы как `DateTime`, `long` и `string`.</span><span class="sxs-lookup"><span data-stu-id="89108-213">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="89108-214">Без настраиваемого преобразователя десериализация помещает `JsonElement` в каждое свойство.</span><span class="sxs-lookup"><span data-stu-id="89108-214">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="89108-215">В [папке модульного теста](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` содержится больше примеров настраиваемых преобразователей, обрабатывающих десериализацию свойств `object`.</span><span class="sxs-lookup"><span data-stu-id="89108-215">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="89108-216">Поддержка словаря с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="89108-216">Support Dictionary with non-string key</span></span>

<span data-ttu-id="89108-217">Встроенная поддержка коллекций словарей предназначена для `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="89108-217">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="89108-218">То есть ключ должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="89108-218">That is, the key must be a string.</span></span> <span data-ttu-id="89108-219">Для поддержки словаря с целым числом или другим типом в качестве ключа нужен настраиваемый преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-219">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="89108-220">В следующем примере кода показан настраиваемый преобразователь, который работает с `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="89108-220">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="89108-221">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-221">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="89108-222">Преобразователь может сериализовать и десериализировать свойство `TemperatureRanges` следующего класса, который использует `Enum`.</span><span class="sxs-lookup"><span data-stu-id="89108-222">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="89108-223">Выходные данные JSON из сериализации выглядят так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="89108-223">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="89108-224">В [папке модульного теста](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` содержится больше примеров настраиваемых преобразователей, обрабатывающих словари с ключом, не являющимся строкой.</span><span class="sxs-lookup"><span data-stu-id="89108-224">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="89108-225">Поддержка полиморфной десериализации</span><span class="sxs-lookup"><span data-stu-id="89108-225">Support polymorphic deserialization</span></span>

<span data-ttu-id="89108-226">Встроенные функции предоставляют ограниченный диапазон [полиморфной сериализации](system-text-json-how-to.md#serialize-properties-of-derived-classes), но совсем не поддерживают десериализацию.</span><span class="sxs-lookup"><span data-stu-id="89108-226">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="89108-227">Для десериализации требуется настраиваемый преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-227">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="89108-228">Например, предположим, что имеется абстрактный базовый класс `Person` с производными классами `Employee` и `Customer`.</span><span class="sxs-lookup"><span data-stu-id="89108-228">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="89108-229">Полиморфная десериализации означает, что во время разработки можно указать `Person` в качестве цели десериализации, а объекты `Customer` и `Employee` в JSON правильно десериализованы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="89108-229">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="89108-230">Во время десериализации необходимо найти признаки, которые определяют требуемый тип в JSON.</span><span class="sxs-lookup"><span data-stu-id="89108-230">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="89108-231">В каждом сценарии доступны различные типы признаков.</span><span class="sxs-lookup"><span data-stu-id="89108-231">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="89108-232">Например, может быть доступно свойство дискриминатора или придется полагаться на присутствие или отсутствие конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="89108-232">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="89108-233">В текущем выпуске `System.Text.Json` не предоставлены атрибуты для указания способов обработки сценариев полиморфной десериализации, поэтому необходимо использовать настраиваемые преобразователи.</span><span class="sxs-lookup"><span data-stu-id="89108-233">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="89108-234">В следующем коде показан базовый класс, два производных класса и настраиваемый преобразователь для них.</span><span class="sxs-lookup"><span data-stu-id="89108-234">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="89108-235">Преобразователь использует свойство дискриминатора для выполнения в полиморфной десериализации.</span><span class="sxs-lookup"><span data-stu-id="89108-235">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="89108-236">Дискриминатор типа не находится в определениях классов, но создается во время сериализации и считывается во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="89108-236">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="89108-237">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-237">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="89108-238">Преобразователь может десериализировать JSON, созданный с помощью того же преобразователя для сериализации, например.</span><span class="sxs-lookup"><span data-stu-id="89108-238">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

<span data-ttu-id="89108-239">Код преобразователя в предыдущем примере считывает и записывает каждое свойство вручную.</span><span class="sxs-lookup"><span data-stu-id="89108-239">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="89108-240">Альтернативой является вызов `Deserialize` или `Serialize` для выполнения некоторых операций.</span><span class="sxs-lookup"><span data-stu-id="89108-240">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="89108-241">Пример см. в [этой публикации на сайте StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="89108-241">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="89108-242">Поддержка кругового пути для Stack\<T></span><span class="sxs-lookup"><span data-stu-id="89108-242">Support round-trip for Stack\<T></span></span>

<span data-ttu-id="89108-243">Если десериализовать строку JSON в объект <xref:System.Collections.Generic.Stack%601>, а затем сериализовать этот объект, содержимое стека будет организовано в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="89108-243">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="89108-244">Это поведение применимо к следующим типам и интерфейсу, а также пользовательским типам, производным от них:</span><span class="sxs-lookup"><span data-stu-id="89108-244">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="89108-245">Чтобы включить поддержку сериализации и десериализации, сохраняющей исходный порядок в стеке, требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-245">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="89108-246">В следующем коде показан пользовательский преобразователь, включающий поддержку кругового пути для объектов `Stack<T>`:</span><span class="sxs-lookup"><span data-stu-id="89108-246">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs)]

<span data-ttu-id="89108-247">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="89108-247">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs?name=SnippetRegister)]

## <a name="other-custom-converter-samples"></a><span data-ttu-id="89108-248">Другие примеры настраиваемых преобразователей</span><span class="sxs-lookup"><span data-stu-id="89108-248">Other custom converter samples</span></span>

<span data-ttu-id="89108-249">В статье о [миграции из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) приведены дополнительные примеры настраиваемых преобразователей.</span><span class="sxs-lookup"><span data-stu-id="89108-249">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="89108-250">В [папке модульных тестов](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в исходном коде `System.Text.Json.Serialization` есть и другие примеры настраиваемых преобразователей, например:</span><span class="sxs-lookup"><span data-stu-id="89108-250">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="89108-251">[Преобразователь Int32, который преобразовывает значение NULL в 0 при десериализации](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs).</span><span class="sxs-lookup"><span data-stu-id="89108-251">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="89108-252">[Преобразователь Int32, который допускает как строковые, так и числовые значения при десериализации](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs).</span><span class="sxs-lookup"><span data-stu-id="89108-252">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="89108-253">[Преобразователь Enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs).</span><span class="sxs-lookup"><span data-stu-id="89108-253">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="89108-254">Преобразователь [List\<T>, который принимает внешние данные](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="89108-254">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="89108-255">[Преобразователь Long[], который работает с разделенным запятыми списком чисел](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="89108-255">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="89108-256">Если необходимо создать преобразователь, изменяющий поведение существующего встроенного преобразователя, можно получить [исходный код существующего преобразователя](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) в качестве отправной точки для настройки.</span><span class="sxs-lookup"><span data-stu-id="89108-256">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89108-257">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="89108-257">Additional resources</span></span>

* <span data-ttu-id="89108-258">[Исходный код для встроенных преобразователей](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="89108-258">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* [<span data-ttu-id="89108-259">Поддержка DateTime и DateTimeOffset в System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89108-259">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="89108-260">Общие сведения о System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89108-260">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="89108-261">Как использовать System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89108-261">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="89108-262">Как выполнить миграцию из Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="89108-262">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* <span data-ttu-id="89108-263">[Справочник по API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="89108-263">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="89108-264">[Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="89108-264">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
