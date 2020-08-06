---
title: Руководство по программированию на C#. Использование индексаторов
description: Сведения об объявлении и использовании индексатора для класса, структуры или интерфейса при программировании на C#. Эта статья содержит пример кода.
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: a8a9e05c1d2e44841177a924c6ff51c6c9e6a05a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301870"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="49fef-104">Использование индексаторов. Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="49fef-104">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="49fef-105">Применение индексаторов упрощает работу с синтаксисом, позволяя создавать [классы](../../language-reference/keywords/class.md), [структуры](../../language-reference/builtin-types/struct.md) и [интерфейсы](../../language-reference/keywords/interface.md), к которым клиентские приложения могут обращаться так же, как к массиву.</span><span class="sxs-lookup"><span data-stu-id="49fef-105">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="49fef-106">В этом случае компилятор создает свойство `Item` (или свойство с другим именем, если присутствует <xref:System.Runtime.CompilerServices.IndexerNameAttribute>) и соответствующие методы доступа.</span><span class="sxs-lookup"><span data-stu-id="49fef-106">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="49fef-107">Индексаторы чаще всего реализуются в типах, предназначенных преимущественно для инкапсуляции внутренней коллекции или массива.</span><span class="sxs-lookup"><span data-stu-id="49fef-107">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="49fef-108">Допустим, у вас есть класс `TempRecord`, представляющий журнал с 10 измерениями температуры по шкале Фаренгейта за период в 24 часа.</span><span class="sxs-lookup"><span data-stu-id="49fef-108">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="49fef-109">Этот класс содержит массив `temps` типа `float[]` для хранения значений температуры.</span><span class="sxs-lookup"><span data-stu-id="49fef-109">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="49fef-110">Реализация индексатора в этом классе позволит клиентам получать доступ к значениям температуры в экземпляре `TempRecord`, используя `float temp = tempRecord[4]` вместо `float temp = tempRecord.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="49fef-110">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="49fef-111">Это позволяет не только упростить синтаксис клиентских приложений, но и облегчить понимание кода класса и его предназначения другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="49fef-111">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="49fef-112">Чтобы объявить индексатор для класса или структуры, используйте ключевое слово [this](../../language-reference/keywords/this.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="49fef-112">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="49fef-113">При объявлении индексатора для объекта автоматически создается свойство с именем `Item`.</span><span class="sxs-lookup"><span data-stu-id="49fef-113">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="49fef-114">Свойство `Item` не будет доступно непосредственно из [выражения доступа к члену](../../language-reference/operators/member-access-operators.md#member-access-expression-) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="49fef-114">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="49fef-115">Кроме того, если вы добавите к объекту с индексатором собственное свойство `Item`, возникнет [ошибка компилятора CS0102](../../misc/cs0102.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-115">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="49fef-116">Чтобы избежать этого, используйте <xref:System.Runtime.CompilerServices.IndexerNameAttribute>, чтобы переименовать индексатор, как описывается ниже.</span><span class="sxs-lookup"><span data-stu-id="49fef-116">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="49fef-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="49fef-117">Remarks</span></span>

<span data-ttu-id="49fef-118">Тип индексатора и типы его параметров должны иметь по крайней мере такой же уровень доступности, как и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="49fef-118">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="49fef-119">Дополнительные сведения об уровнях доступа см. в разделе [Модификаторы доступа](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-119">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="49fef-120">Дополнительные сведения об использовании индексаторов с интерфейсом см. в разделе [Индексаторы интерфейса](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-120">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="49fef-121">Сигнатура индексатора определяет число и типы его формальных параметров.</span><span class="sxs-lookup"><span data-stu-id="49fef-121">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="49fef-122">В ней не указываются тип индексатора или имена его формальных параметров.</span><span class="sxs-lookup"><span data-stu-id="49fef-122">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="49fef-123">Если для одного класса объявляется несколько индексаторов, они должны иметь разные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="49fef-123">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="49fef-124">Значение индексатора не классифицируется как переменная и, соответственно, не может передаваться в качестве параметра [ref](../../language-reference/keywords/ref.md) или [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-124">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="49fef-125">Чтобы присвоить индексатору имя, которое можно использовать в других языках, используйте <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="49fef-125">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="49fef-126">Этот индексатор будет иметь имя `TheItem`, поскольку оно переопределено атрибутом имени индексатора.</span><span class="sxs-lookup"><span data-stu-id="49fef-126">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="49fef-127">По умолчанию используется имя индексатора `Item`.</span><span class="sxs-lookup"><span data-stu-id="49fef-127">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="49fef-128">Пример 1</span><span class="sxs-lookup"><span data-stu-id="49fef-128">Example 1</span></span>

<span data-ttu-id="49fef-129">В следующем примере показано, как объявить частное поле массива `temps` и индексатор.</span><span class="sxs-lookup"><span data-stu-id="49fef-129">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="49fef-130">Индексатор обеспечивает прямой доступ к экземпляру `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="49fef-130">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="49fef-131">Вместо использования индексатора можно объявить массив как элемент [public](../../language-reference/keywords/public.md) и осуществлять доступ к его элементам напрямую (`tempRecord.temps[i]`).</span><span class="sxs-lookup"><span data-stu-id="49fef-131">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="49fef-132">Обратите внимание, что при определении прав доступа индексатора, например в инструкции `Console.Write`, вызывается метод доступа [get](../../language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-132">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="49fef-133">Таким образом, если метод доступа `get` отсутствует, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="49fef-133">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="49fef-134">Индексирование с использованием других значений</span><span class="sxs-lookup"><span data-stu-id="49fef-134">Indexing using other values</span></span>

<span data-ttu-id="49fef-135">В C# тип параметра индексатора не ограничивается целочисленными значениями.</span><span class="sxs-lookup"><span data-stu-id="49fef-135">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="49fef-136">Например, в качестве индексатора могут использоваться строки.</span><span class="sxs-lookup"><span data-stu-id="49fef-136">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="49fef-137">Такой индексатор можно реализовать путем поиска строки в коллекции с возвратом соответствующего значения.</span><span class="sxs-lookup"><span data-stu-id="49fef-137">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="49fef-138">Поскольку методы доступа можно перегружать, строковые и целочисленные версии могут сосуществовать.</span><span class="sxs-lookup"><span data-stu-id="49fef-138">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="49fef-139">Пример 2</span><span class="sxs-lookup"><span data-stu-id="49fef-139">Example 2</span></span>

<span data-ttu-id="49fef-140">Этот пример объявляет класс, который хранит названия дней недели.</span><span class="sxs-lookup"><span data-stu-id="49fef-140">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="49fef-141">Метод доступа `get` принимает название дня в виде строкового значения и возвращает соответствующее целое число.</span><span class="sxs-lookup"><span data-stu-id="49fef-141">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="49fef-142">Например, для Sunday возвращается значение 0, для Monday — 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="49fef-142">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="49fef-143">Пример использования 2</span><span class="sxs-lookup"><span data-stu-id="49fef-143">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="49fef-144">Пример 3</span><span class="sxs-lookup"><span data-stu-id="49fef-144">Example 3</span></span>

<span data-ttu-id="49fef-145">В этом примере объявляется класс, в котором хранятся названия дней недели с использованием перечисления <xref:System.DayOfWeek?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="49fef-145">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="49fef-146">Метод доступа `get` принимает название дня (`DayOfWeek`) в виде строкового значения и возвращает соответствующее целое число.</span><span class="sxs-lookup"><span data-stu-id="49fef-146">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="49fef-147">Например, для `DayOfWeek.Sunday` возвращается 0, для `DayOfWeek.Monday` — 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="49fef-147">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="49fef-148">Пример использования 3</span><span class="sxs-lookup"><span data-stu-id="49fef-148">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="49fef-149">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="49fef-149">Robust programming</span></span>

<span data-ttu-id="49fef-150">Повысить безопасность и надежность индексаторов можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="49fef-150">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="49fef-151">Реализуйте стратегию обработки ошибок, предусматривающую действия в ситуациях, когда из клиентского кода передается недопустимое значение индекса.</span><span class="sxs-lookup"><span data-stu-id="49fef-151">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="49fef-152">В первом примере из этого раздела класс TempRecord содержит свойство Length, с помощью которого клиентский код проверяет введенное значение, прежде чем передать его в индексатор.</span><span class="sxs-lookup"><span data-stu-id="49fef-152">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="49fef-153">Кроме того, код обработки ошибок можно поместить в сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="49fef-153">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="49fef-154">Не забудьте задокументировать исключения, которые будут вызываться в методе доступа индексатора, для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="49fef-154">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="49fef-155">Настройте максимально ограничивающие уровни доступа для методов доступа [get](../../language-reference/keywords/get.md) и [set](../../language-reference/keywords/set.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-155">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="49fef-156">Особенно важно сделать это для метода доступа `set`.</span><span class="sxs-lookup"><span data-stu-id="49fef-156">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="49fef-157">Дополнительные сведения см. в разделе [Доступность методов доступа](../classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-157">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49fef-158">См. также</span><span class="sxs-lookup"><span data-stu-id="49fef-158">See also</span></span>

- [<span data-ttu-id="49fef-159">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="49fef-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="49fef-160">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="49fef-160">Indexers</span></span>](./index.md)
- [<span data-ttu-id="49fef-161">Свойства</span><span class="sxs-lookup"><span data-stu-id="49fef-161">Properties</span></span>](../classes-and-structs/properties.md)
