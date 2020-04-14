---
title: Тип данных Decimal
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243327"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="0cc1c-102">Тип данных Decimal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cc1c-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="0cc1c-103">Содержит 128-разрядные (16-байтные) значения со знаком, представляющие 96-разрядные (12-байтные) целые числа с переменной степенью, кратной 10.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="0cc1c-104">Коэффициент масштабирования определяет количество цифр справа от десятичной точки; она колеблется от 0 до 28.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="0cc1c-105">С шкалой 0 (без десятичных мест), максимально возможное значение составляет 79,228,162,514,264,337,593,543,950,335 (No /-7,92281625511144355933334433344330E-28).</span><span class="sxs-lookup"><span data-stu-id="0cc1c-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="0cc1c-106">С 28 десятичных мест, наибольшее значение является No / 7,922816251426337593543950335, и наименьшее ненулевое значение является No / 0,0000000000000000000000000000000000 (/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="0cc1c-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="0cc1c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0cc1c-107">Remarks</span></span>

<span data-ttu-id="0cc1c-108">Тип `Decimal` данных обеспечивает наибольшее количество значительных цифр для числа.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="0cc1c-109">Он поддерживает до 29 значительных цифр и может представлять значения, превышающие 7,9228 х 10 х 28.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="0cc1c-110">Он особенно подходит для расчетов, таких как финансовые, которые требуют большого количества цифр, но не могут мириться с ошибками округления.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="0cc1c-111">Значение по умолчанию для типа `Decimal` — 0.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="0cc1c-112">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0cc1c-112">Programming Tips</span></span>

- <span data-ttu-id="0cc1c-113">**Точность.**</span><span class="sxs-lookup"><span data-stu-id="0cc1c-113">**Precision.**</span></span> <span data-ttu-id="0cc1c-114">`Decimal`не является типом данных плавающей точки.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="0cc1c-115">Структура `Decimal` содержит двоичное значение рядом, вместе с битом знака и коэффициентом масштабирования, который определяет, какая часть значения является десятичной фракцией.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="0cc1c-116">Из-за `Decimal` этого, числа имеют более точное представление в`Single` `Double`памяти, чем плавающие точки типов (и ).</span><span class="sxs-lookup"><span data-stu-id="0cc1c-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="0cc1c-117">**Производительности.**</span><span class="sxs-lookup"><span data-stu-id="0cc1c-117">**Performance.**</span></span> <span data-ttu-id="0cc1c-118">Тип `Decimal` данных является самым медленным из всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="0cc1c-119">Прежде чем выбирать тип данных, следует взвесить важность точности с производительностью.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="0cc1c-120">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="0cc1c-120">**Widening.**</span></span> <span data-ttu-id="0cc1c-121">Тип `Decimal` данных расширяется до `Single` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="0cc1c-122">Это означает, `Decimal` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="0cc1c-123">**Трейлинг Ноль.**</span><span class="sxs-lookup"><span data-stu-id="0cc1c-123">**Trailing Zeros.**</span></span> <span data-ttu-id="0cc1c-124">Visual Basic не хранит задние `Decimal` нули в буквальном смысле.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="0cc1c-125">Тем не `Decimal` менее, переменная сохраняет любые задние нули, приобретенные в расчете.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="0cc1c-126">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="0cc1c-127">Выход `MsgBox` в предыдущем примере заключается в следующем:</span><span class="sxs-lookup"><span data-stu-id="0cc1c-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="0cc1c-128">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="0cc1c-128">**Type Characters.**</span></span> <span data-ttu-id="0cc1c-129">При добавлении к литералу символа типа литерала `D` производится принудительное приведение литерала к типу данных `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="0cc1c-130">При добавлении символа идентификатора типа `@` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="0cc1c-131">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="0cc1c-131">**Framework Type.**</span></span> <span data-ttu-id="0cc1c-132">В .NET Framework данный тип соответствует структуре <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="0cc1c-133">Диапазон</span><span class="sxs-lookup"><span data-stu-id="0cc1c-133">Range</span></span>

 <span data-ttu-id="0cc1c-134">Возможно, потребуется `D` использовать символ типа для присвоения большого значения переменной или постоянной. `Decimal`</span><span class="sxs-lookup"><span data-stu-id="0cc1c-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="0cc1c-135">Это требование объясняется тем, что компилятор интерпретирует буквальный как `Long` если бы персонаж буквального типа не следовал буквальному, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="0cc1c-136">Декларация `bigDec1` не производит переполнения, потому что значение, которое назначено `Long`ему, подпадает под диапазон.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="0cc1c-137">Значение `Long` может быть присвоено `Decimal` переменной.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="0cc1c-138">Декларация `bigDec2` для генерирует ошибку переполнения, поскольку значение, назначенное ей, слишком велико для. `Long`</span><span class="sxs-lookup"><span data-stu-id="0cc1c-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="0cc1c-139">Поскольку числовой буквальный не может быть `Long`сначала истолкован как, `Decimal` он не может быть назначен переменной.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="0cc1c-140">Ибо, `bigDec3`буквального `D` типа символ решает проблему, заставляя компилятор `Decimal` интерпретировать буквальное как вместо как `Long`.</span><span class="sxs-lookup"><span data-stu-id="0cc1c-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cc1c-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0cc1c-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0cc1c-142">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0cc1c-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0cc1c-143">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="0cc1c-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="0cc1c-144">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="0cc1c-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="0cc1c-145">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="0cc1c-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0cc1c-146">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0cc1c-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0cc1c-147">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0cc1c-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
