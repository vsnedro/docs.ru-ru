---
title: Перечисления
description: 'Узнайте, как использовать перечисления F # вместо литералов, чтобы сделать код более читаемым и удобным в обслуживании.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812111"
---
# <a name="enumerations"></a><span data-ttu-id="c7556-103">Перечисления</span><span class="sxs-lookup"><span data-stu-id="c7556-103">Enumerations</span></span>

<span data-ttu-id="c7556-104">*Перечисления*, также известные как *перечисления*, являются целочисленными типами, где метки присваиваются подмножеству значений.</span><span class="sxs-lookup"><span data-stu-id="c7556-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="c7556-105">Их можно использовать вместо литералов, чтобы сделать код более понятным и простым в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="c7556-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7556-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7556-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="c7556-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c7556-107">Remarks</span></span>

<span data-ttu-id="c7556-108">Перечисление во многом похоже на размеченное объединение с простыми значениями, за исключением того, что можно указать значения.</span><span class="sxs-lookup"><span data-stu-id="c7556-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="c7556-109">Значениями обычно являются целые числа, начинающиеся с 0 или 1, или целые числа, представляющие битовые позиции.</span><span class="sxs-lookup"><span data-stu-id="c7556-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="c7556-110">Если перечисление предназначено для представления битовых позиций, следует также использовать атрибут [flags](xref:System.FlagsAttribute) .</span><span class="sxs-lookup"><span data-stu-id="c7556-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="c7556-111">Базовый тип перечисления определяется из используемого литерала, поэтому, например, можно использовать литералы с суффиксом, например `1u` , `2u` и т. д., для типа целого числа без знака ( `uint32` ).</span><span class="sxs-lookup"><span data-stu-id="c7556-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="c7556-112">При ссылке на именованные значения необходимо использовать имя самого типа перечисления в качестве квалификатора, то есть, а `enum-name.value1` не только `value1` .</span><span class="sxs-lookup"><span data-stu-id="c7556-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="c7556-113">Это поведение отличается от различенных объединений.</span><span class="sxs-lookup"><span data-stu-id="c7556-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="c7556-114">Это происходит потому, что перечисления всегда имеют атрибут [рекуирекуалифиедакцесс](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="c7556-114">This is because enumerations always have the [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) attribute.</span></span>

<span data-ttu-id="c7556-115">В следующем коде показано объявление и использование перечисления.</span><span class="sxs-lookup"><span data-stu-id="c7556-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="c7556-116">Можно легко преобразовать перечисления в базовый тип с помощью соответствующего оператора, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c7556-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="c7556-117">Перечисляемые типы могут иметь один из следующих базовых типов: `sbyte` , `byte` ,, `int16` , `uint16` `int32` , `uint32` , `int64` , `uint16` , `uint64` и `char` .</span><span class="sxs-lookup"><span data-stu-id="c7556-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="c7556-118">Типы перечисления представлены в .NET Framework как типы, унаследованные от `System.Enum` , которые, в свою очередь, наследуются от `System.ValueType` .</span><span class="sxs-lookup"><span data-stu-id="c7556-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="c7556-119">Таким образом, они являются типами значений, расположенными в стеке или встроенными в содержащий их объект, а любое значение базового типа является допустимым значением перечисления.</span><span class="sxs-lookup"><span data-stu-id="c7556-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="c7556-120">Это важно при сопоставлении шаблонов со значениями перечисления, поскольку необходимо предоставить шаблон, который перехватывает неименованные значения.</span><span class="sxs-lookup"><span data-stu-id="c7556-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="c7556-121">`enum`Функцию в библиотеке F # можно использовать для создания значения перечисления, даже для значения, отличного от одного из стандартных именованных значений.</span><span class="sxs-lookup"><span data-stu-id="c7556-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="c7556-122">Используйте `enum` функцию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c7556-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="c7556-123">Функция по умолчанию `enum` работает с типом `int32` .</span><span class="sxs-lookup"><span data-stu-id="c7556-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="c7556-124">Поэтому его нельзя использовать с типами перечисления, имеющими другие базовые типы.</span><span class="sxs-lookup"><span data-stu-id="c7556-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="c7556-125">Вместо этого используйте следующий.</span><span class="sxs-lookup"><span data-stu-id="c7556-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="c7556-126">Кроме того, варианты для перечислений всегда создаются как `public` .</span><span class="sxs-lookup"><span data-stu-id="c7556-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="c7556-127">Это сделано так, чтобы они совпадали с C# и остальной частью платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="c7556-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7556-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c7556-128">See also</span></span>

- [<span data-ttu-id="c7556-129">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="c7556-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c7556-130">Приведение и преобразование</span><span class="sxs-lookup"><span data-stu-id="c7556-130">Casting and Conversions</span></span>](casting-and-conversions.md)
