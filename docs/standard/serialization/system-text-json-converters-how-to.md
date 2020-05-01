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
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159576"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="d4db9-102">Как написать настраиваемые преобразователи для сериализации JSON (маршалинг) в .NET</span><span class="sxs-lookup"><span data-stu-id="d4db9-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="d4db9-103">В этой статье показано, как создать настраиваемые преобразователи для классов сериализации JSON, предоставляемых в пространстве имен <xref:[!OP.NO-LOC(System.Text.Json)]>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:[!OP.NO-LOC(System.Text.Json)]> namespace.</span></span> <span data-ttu-id="d4db9-104">Общие сведения о `[!OP.NO-LOC(System.Text.Json)]` см. в статье [Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="d4db9-104">For an introduction to `[!OP.NO-LOC(System.Text.Json)]`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="d4db9-105">*Преобразователь* — это класс, который преобразует объект или значение в формат JSON и обратно.</span><span class="sxs-lookup"><span data-stu-id="d4db9-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="d4db9-106">Пространство имен `[!OP.NO-LOC(System.Text.Json)]` содержит встроенные преобразователи для большинства примитивных типов, которые сопоставляются с примитивами JavaScript.</span><span class="sxs-lookup"><span data-stu-id="d4db9-106">The `[!OP.NO-LOC(System.Text.Json)]` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="d4db9-107">Вы можете создавать настраиваемые преобразователи для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="d4db9-107">You can write custom converters:</span></span>

* <span data-ttu-id="d4db9-108">Чтобы переопределить поведение встроенного преобразователя, используемое по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d4db9-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="d4db9-109">Например, может потребоваться, чтобы значения `DateTime` были представлены в формате дд.мм.гггг вместо формата ISO 8601-1:2019 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d4db9-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="d4db9-110">Для поддержки настраиваемого типа значения.</span><span class="sxs-lookup"><span data-stu-id="d4db9-110">To support a custom value type.</span></span> <span data-ttu-id="d4db9-111">Например, структуры `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="d4db9-112">Вы также можете создать настраиваемые преобразователи для настройки или расширения `[!OP.NO-LOC(System.Text.Json)]` с функциональностью, не входящей в текущий выпуск.</span><span class="sxs-lookup"><span data-stu-id="d4db9-112">You can also write custom converters to customize or extend `[!OP.NO-LOC(System.Text.Json)]` with functionality not included in the current release.</span></span> <span data-ttu-id="d4db9-113">Далее в этой статье описываются следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="d4db9-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="d4db9-114">[Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="d4db9-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="d4db9-115">[Поддержка словаря с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="d4db9-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="d4db9-116">[Поддержка полиморфной десериализации](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="d4db9-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="d4db9-117">Шаблоны настраиваемых преобразователей</span><span class="sxs-lookup"><span data-stu-id="d4db9-117">Custom converter patterns</span></span>

<span data-ttu-id="d4db9-118">Существует два шаблона для создания настраиваемого преобразователя: базовый шаблон и шаблон фабрики.</span><span class="sxs-lookup"><span data-stu-id="d4db9-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="d4db9-119">Шаблон фабрики предназначен для преобразователей, обрабатывающих типы `Enum` или открытые универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="d4db9-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="d4db9-120">Базовый шаблон предназначен для неуниверсальных и закрытых универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="d4db9-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="d4db9-121">Например, для преобразователей следующих типов требуется шаблон фабрики:</span><span class="sxs-lookup"><span data-stu-id="d4db9-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="d4db9-122">Ниже приведены некоторые примеры типов, которые могут быть обработаны базовым шаблоном:</span><span class="sxs-lookup"><span data-stu-id="d4db9-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="d4db9-123">Базовый шаблон создает класс, который может работать с одним типом.</span><span class="sxs-lookup"><span data-stu-id="d4db9-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="d4db9-124">Шаблон фабрики создает класс, который в среде выполнения определяет, какой конкретный тип необходим, и динамически создает соответствующий преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="d4db9-125">Пример базового преобразователя</span><span class="sxs-lookup"><span data-stu-id="d4db9-125">Sample basic converter</span></span>

<span data-ttu-id="d4db9-126">Следующий пример представляет собой преобразователь, который переопределяет сериализацию по умолчанию для существующего типа данных.</span><span class="sxs-lookup"><span data-stu-id="d4db9-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="d4db9-127">Для свойств `DateTimeOffset` преобразователь использует формат дд.мм.гггг.</span><span class="sxs-lookup"><span data-stu-id="d4db9-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="d4db9-128">Пример преобразователя шаблона фабрики</span><span class="sxs-lookup"><span data-stu-id="d4db9-128">Sample factory pattern converter</span></span>

<span data-ttu-id="d4db9-129">В следующем примере кода показан настраиваемый преобразователь, который работает с `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="d4db9-130">Код соответствует шаблону фабрики, так как первый параметр универсального типа является `Enum`, а второй — открытым.</span><span class="sxs-lookup"><span data-stu-id="d4db9-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="d4db9-131">Метод `CanConvert` возвращает `true` только для `Dictionary` с двумя универсальными параметрами, первый из которых является типом `Enum`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="d4db9-132">Внутренний преобразователь получает существующий преобразователь для работы с любым типом, предоставленным во время выполнения для `TValue`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="d4db9-133">Предыдущий код аналогичен тому, который приведен в разделе [Поддержка словаря с ключом, не являющимся строкой](#support-dictionary-with-non-string-key) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d4db9-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="d4db9-134">Инструкции по базовому шаблону</span><span class="sxs-lookup"><span data-stu-id="d4db9-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="d4db9-135">Ниже описывается, как создать преобразователь с помощью базового шаблона:</span><span class="sxs-lookup"><span data-stu-id="d4db9-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="d4db9-136">Создайте класс, производный от <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601>, где `T` — это тип для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="d4db9-136">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="d4db9-137">Переопределите метод `Read`, чтобы десериализировать входящие данные JSON и преобразовать их в тип `T`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="d4db9-138">Для чтения JSON используйте передаваемое в метод значение <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-138">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="d4db9-139">Переопределите метод `Write` для сериализации входящего объекта типа `T`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="d4db9-140">Для записи JSON используйте передаваемое в метод значение <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-140">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="d4db9-141">Переопределяйте метод `CanConvert` только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d4db9-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="d4db9-142">Реализация по умолчанию возвращает `true`, если тип для преобразования имеет тип `T`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="d4db9-143">Поэтому для преобразователей, поддерживающих только тип `T`, не требуется переопределять этот метод.</span><span class="sxs-lookup"><span data-stu-id="d4db9-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="d4db9-144">Пример преобразователя, в котором требуется переопределить этот метод, см. в разделе [Поддержка полиморфной десериализации](#support-polymorphic-deserialization) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d4db9-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="d4db9-145">Вы можете ссылаться на [исходный код встроенных преобразователей](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) в качестве эталонных реализаций для написания настраиваемых преобразователей.</span><span class="sxs-lookup"><span data-stu-id="d4db9-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="d4db9-146">Инструкции по шаблону фабрики</span><span class="sxs-lookup"><span data-stu-id="d4db9-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="d4db9-147">Ниже описывается, как создать преобразователь с помощью шаблона фабрики:</span><span class="sxs-lookup"><span data-stu-id="d4db9-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="d4db9-148">Создайте класс, наследующий от класса <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-148">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="d4db9-149">Переопределите метод `CanConvert`, чтобы он возвращал значение true, если преобразователь может обрабатывать этот тип.</span><span class="sxs-lookup"><span data-stu-id="d4db9-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="d4db9-150">Например, если преобразователь предназначен для `List<T>`, он может обрабатывать только `List<int>`, `List<string>` и `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="d4db9-151">Переопределите метод `CreateConverter`, чтобы он возвращал экземпляр класса преобразователя, обрабатывающего тип для преобразования, который будет предоставлен во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4db9-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="d4db9-152">Создайте класс преобразователя с помощью метода `CreateConverter`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-152">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="d4db9-153">Шаблон фабрики необходим для открытых универсальных шаблонов, так как код для преобразования объекта в строку и обратно не совпадает для всех типов.</span><span class="sxs-lookup"><span data-stu-id="d4db9-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="d4db9-154">Преобразователь для открытого универсального типа (например, `List<T>`) должен создать преобразователь для закрытого универсального типа (например, `List<DateTime>`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="d4db9-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="d4db9-155">Необходимо написать код для обработки каждого закрытого универсального типа, который может обрабатывать преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="d4db9-156">Тип `Enum` похож на открытый универсальный тип: преобразователь для `Enum` должен создать преобразователь для определенного типа `Enum` (например, `WeekdaysEnum`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="d4db9-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="d4db9-157">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="d4db9-157">Error handling</span></span>

<span data-ttu-id="d4db9-158">Если необходимо вызвать исключение в коде обработки ошибок, рассмотрите возможность создания <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> без сообщения.</span><span class="sxs-lookup"><span data-stu-id="d4db9-158">If you need to throw an exception in error-handling code, consider throwing a <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> without a message.</span></span> <span data-ttu-id="d4db9-159">Этот тип исключения автоматически создает сообщение, содержащее путь к части JSON, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="d4db9-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="d4db9-160">Например, инструкция `throw new JsonException();` выдает сообщение об ошибке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d4db9-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="d4db9-161">Если вы предоставляете сообщение (например, `throw new JsonException("Error occurred")`), исключение по-прежнему предоставляет путь в свойстве <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="d4db9-162">Регистрация настраиваемого преобразователя</span><span class="sxs-lookup"><span data-stu-id="d4db9-162">Register a custom converter</span></span>

<span data-ttu-id="d4db9-163">*Зарегистрируйте* настраиваемый преобразователь, чтобы использовать методы `Serialize` и `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="d4db9-164">Воспользуйтесь одним из перечисленных ниже подходов.</span><span class="sxs-lookup"><span data-stu-id="d4db9-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="d4db9-165">Добавьте экземпляр класса преобразователя в коллекцию <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-165">Add an instance of the converter class to the <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="d4db9-166">Примените атрибут [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) к свойствам, для которых требуется настраиваемый преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-166">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="d4db9-167">Примените атрибут [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) к классу или структуре, представляющей настраиваемый тип значения.</span><span class="sxs-lookup"><span data-stu-id="d4db9-167">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="d4db9-168">Пример регистрации — коллекция преобразователей</span><span class="sxs-lookup"><span data-stu-id="d4db9-168">Registration sample - Converters collection</span></span>

<span data-ttu-id="d4db9-169">Ниже приведен пример, который делает <xref:System.ComponentModel.DateTimeOffsetConverter> классом по умолчанию для свойств типа <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="d4db9-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="d4db9-170">Предположим, что вы сериализуете экземпляр следующего типа.</span><span class="sxs-lookup"><span data-stu-id="d4db9-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="d4db9-171">Ниже приведен пример выходных данных JSON, в котором показано использование настраиваемого преобразователя.</span><span class="sxs-lookup"><span data-stu-id="d4db9-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="d4db9-172">Следующий код использует тот же подход для десериализации с помощью настраиваемого преобразователя `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="d4db9-173">Пример регистрации — [JsonConverter] для свойства</span><span class="sxs-lookup"><span data-stu-id="d4db9-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="d4db9-174">В следующем примере кода выбирается настраиваемый преобразователь для свойства `Date`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="d4db9-175">В коде для сериализации `WeatherForecastWithConverterAttribute` не нужно использовать `JsonSerializeOptions.Converters`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="d4db9-176">В коде для десериализации также не нужно использовать `Converters`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="d4db9-177">Пример регистрации — [JsonConverter] для типа</span><span class="sxs-lookup"><span data-stu-id="d4db9-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="d4db9-178">Ниже приведен код, создающий структуру и применяющий к ней атрибут `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="d4db9-179">Ниже приведен настраиваемый преобразователь для предыдущей структуры.</span><span class="sxs-lookup"><span data-stu-id="d4db9-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="d4db9-180">Атрибут `[JsonConvert]` в структуре регистрирует настраиваемый преобразователь в качестве значения по умолчанию для свойств типа `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="d4db9-181">Этот преобразователь автоматически используется в свойстве `TemperatureCelsius` следующего типа при его сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="d4db9-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="d4db9-182">Очередность регистрации преобразователей</span><span class="sxs-lookup"><span data-stu-id="d4db9-182">Converter registration precedence</span></span>

<span data-ttu-id="d4db9-183">Во время сериализации или десериализации выбирается преобразователь для каждого элемента JSON в следующем порядке — от наивысшего приоритета к наименьшему.</span><span class="sxs-lookup"><span data-stu-id="d4db9-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="d4db9-184">Атрибут `[JsonConverter]` применяется к свойству.</span><span class="sxs-lookup"><span data-stu-id="d4db9-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="d4db9-185">Преобразователь, добавляемый в коллекцию `Converters`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="d4db9-186">Атрибут `[JsonConverter]` применяется к настраиваемому типу значения или POCO.</span><span class="sxs-lookup"><span data-stu-id="d4db9-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="d4db9-187">Если в коллекции `Converters` зарегистрировано несколько настраиваемых преобразователей для типов, то используется первый преобразователь, возвращающий значение true для `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="d4db9-188">Встроенный преобразователь выбирается только в том случае, если соответствующий настраиваемый преобразователь не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="d4db9-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="d4db9-189">Примеры преобразователей для выполнения стандартных сценариев</span><span class="sxs-lookup"><span data-stu-id="d4db9-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="d4db9-190">В следующих разделах приведены примеры преобразователей, в которых рассматриваются распространенные сценарии, необрабатываемые встроенными функциями.</span><span class="sxs-lookup"><span data-stu-id="d4db9-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* <span data-ttu-id="d4db9-191">[Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="d4db9-191">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties)</span></span>
* <span data-ttu-id="d4db9-192">[Поддержка словаря с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="d4db9-192">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key)</span></span>
* <span data-ttu-id="d4db9-193">[Поддержка полиморфной десериализации](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="d4db9-193">[Support polymorphic deserialization](#support-polymorphic-deserialization)</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="d4db9-194">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="d4db9-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="d4db9-195">При десериализации в свойство типа `object` создается объект `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="d4db9-196">Причина заключается в том, что десериализатор не знает, какой тип среды выполнения создать, и не пытается угадать.</span><span class="sxs-lookup"><span data-stu-id="d4db9-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="d4db9-197">Например, если свойство JSON имеет значение true, десериализатор не определит, что значение является `Boolean`, а если у элемента есть значение 01/01/2019, десериализатор не определит, что это `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="d4db9-198">Определение типа может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="d4db9-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="d4db9-199">Если десериализатор анализирует число JSON, не имеющее десятичного разделителя в качестве `long`, это может привести к проблемам в виде выхода за пределы диапазона, если значение первоначально было сериализовано как `ulong` или `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="d4db9-200">Анализ числа с десятичным разделителем в качестве `double` может привести к потере точности, если это число было первоначально сериализовано как `decimal`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="d4db9-201">В следующем коде показан настраиваемый преобразователь для свойств `object` сценариев с определением типа.</span><span class="sxs-lookup"><span data-stu-id="d4db9-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="d4db9-202">Код преобразует:</span><span class="sxs-lookup"><span data-stu-id="d4db9-202">The code converts:</span></span>

* <span data-ttu-id="d4db9-203">`true` и `false` в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="d4db9-204">Числа без десятичного числа в `long`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="d4db9-205">Числа с десятичным числом в `double`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="d4db9-206">Даты в `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="d4db9-207">Строки в `string`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-207">Strings to `string`</span></span>
* <span data-ttu-id="d4db9-208">Все остальное в `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="d4db9-209">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="d4db9-210">Ниже приведен пример типа со свойствами `object`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="d4db9-211">Следующий пример JSON для десериализации содержит значения, которые будут десериализованы как `DateTime`, `long` и `string`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="d4db9-212">Без настраиваемого преобразователя десериализация помещает `JsonElement` в каждое свойство.</span><span class="sxs-lookup"><span data-stu-id="d4db9-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="d4db9-213">В [папке модульного теста](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` содержится больше примеров настраиваемых преобразователей, обрабатывающих десериализацию свойств `object`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="d4db9-214">Поддержка словаря с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="d4db9-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="d4db9-215">Встроенная поддержка коллекций словарей предназначена для `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="d4db9-216">То есть ключ должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="d4db9-216">That is, the key must be a string.</span></span> <span data-ttu-id="d4db9-217">Для поддержки словаря с целым числом или другим типом в качестве ключа нужен настраиваемый преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="d4db9-218">В следующем примере кода показан настраиваемый преобразователь, который работает с `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="d4db9-219">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="d4db9-220">Преобразователь может сериализовать и десериализировать свойство `TemperatureRanges` следующего класса, который использует `Enum`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="d4db9-221">Выходные данные JSON из сериализации выглядят так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d4db9-221">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="d4db9-222">В [папке модульного теста](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` содержится больше примеров настраиваемых преобразователей, обрабатывающих словари с ключом, не являющимся строкой.</span><span class="sxs-lookup"><span data-stu-id="d4db9-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="d4db9-223">Поддержка полиморфной десериализации</span><span class="sxs-lookup"><span data-stu-id="d4db9-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="d4db9-224">Встроенные функции предоставляют ограниченный диапазон [полиморфной сериализации](system-text-json-how-to.md#serialize-properties-of-derived-classes), но совсем не поддерживают десериализацию.</span><span class="sxs-lookup"><span data-stu-id="d4db9-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="d4db9-225">Для десериализации требуется настраиваемый преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="d4db9-226">Например, предположим, что имеется абстрактный базовый класс `Person` с производными классами `Employee` и `Customer`.</span><span class="sxs-lookup"><span data-stu-id="d4db9-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="d4db9-227">Полиморфная десериализации означает, что во время разработки можно указать `Person` в качестве цели десериализации, а объекты `Customer` и `Employee` в JSON правильно десериализованы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4db9-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="d4db9-228">Во время десериализации необходимо найти признаки, которые определяют требуемый тип в JSON.</span><span class="sxs-lookup"><span data-stu-id="d4db9-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="d4db9-229">В каждом сценарии доступны различные типы признаков.</span><span class="sxs-lookup"><span data-stu-id="d4db9-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="d4db9-230">Например, может быть доступно свойство дискриминатора или придется полагаться на присутствие или отсутствие конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="d4db9-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="d4db9-231">В текущем выпуске `System.Text.Json` не предоставлены атрибуты для указания способов обработки сценариев полиморфной десериализации, поэтому необходимо использовать настраиваемые преобразователи.</span><span class="sxs-lookup"><span data-stu-id="d4db9-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="d4db9-232">В следующем коде показан базовый класс, два производных класса и настраиваемый преобразователь для них.</span><span class="sxs-lookup"><span data-stu-id="d4db9-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="d4db9-233">Преобразователь использует свойство дискриминатора для выполнения в полиморфной десериализации.</span><span class="sxs-lookup"><span data-stu-id="d4db9-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="d4db9-234">Дискриминатор типа не находится в определениях классов, но создается во время сериализации и считывается во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="d4db9-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="d4db9-235">В следующем коде регистрируется преобразователь.</span><span class="sxs-lookup"><span data-stu-id="d4db9-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="d4db9-236">Преобразователь может десериализировать JSON, созданный с помощью того же преобразователя для сериализации, например.</span><span class="sxs-lookup"><span data-stu-id="d4db9-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="d4db9-237">Код преобразователя в предыдущем примере считывает и записывает каждое свойство вручную.</span><span class="sxs-lookup"><span data-stu-id="d4db9-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="d4db9-238">Альтернативой является вызов `Deserialize` или `Serialize` для выполнения некоторых операций.</span><span class="sxs-lookup"><span data-stu-id="d4db9-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="d4db9-239">Пример см. в [этой публикации на сайте StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="d4db9-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="d4db9-240">Другие примеры настраиваемых преобразователей</span><span class="sxs-lookup"><span data-stu-id="d4db9-240">Other custom converter samples</span></span>

<span data-ttu-id="d4db9-241">В статье о [миграции из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) приведены дополнительные примеры настраиваемых преобразователей.</span><span class="sxs-lookup"><span data-stu-id="d4db9-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="d4db9-242">В [папке модульных тестов](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в исходном коде `System.Text.Json.Serialization` есть и другие примеры настраиваемых преобразователей, например:</span><span class="sxs-lookup"><span data-stu-id="d4db9-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="d4db9-243">[Преобразователь Int32, который преобразовывает значение NULL в 0 при десериализации](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs).</span><span class="sxs-lookup"><span data-stu-id="d4db9-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="d4db9-244">[Преобразователь Int32, который допускает как строковые, так и числовые значения при десериализации](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs).</span><span class="sxs-lookup"><span data-stu-id="d4db9-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="d4db9-245">[Преобразователь Enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs).</span><span class="sxs-lookup"><span data-stu-id="d4db9-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="d4db9-246">[Преобразователь List\<T>, который принимает внешние данные](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs).</span><span class="sxs-lookup"><span data-stu-id="d4db9-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="d4db9-247">[Преобразователь Long[], который работает с разделенным запятыми списком чисел](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="d4db9-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="d4db9-248">Если необходимо создать преобразователь, изменяющий поведение существующего встроенного преобразователя, можно получить [исходный код существующего преобразователя](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) в качестве отправной точки для настройки.</span><span class="sxs-lookup"><span data-stu-id="d4db9-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4db9-249">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d4db9-249">Additional resources</span></span>

* <span data-ttu-id="d4db9-250">[Исходный код для встроенных преобразователей](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="d4db9-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="d4db9-251">[Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="d4db9-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="d4db9-252">[Общие сведения о System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4db9-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="d4db9-253">[Как использовать System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="d4db9-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="d4db9-254">[Как выполнить миграцию из Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="d4db9-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="d4db9-255">[Справочник по API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="d4db9-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="d4db9-256">[Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="d4db9-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
