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
ms.openlocfilehash: 690c8061b6df1115aa24668520170b44edfa8287
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415651"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="d625c-102">Тип данных Decimal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d625c-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="d625c-103">Содержит 128-разрядные (16-байтные) значения со знаком, представляющие 96-разрядные (12-байтные) целые числа с переменной степенью, кратной 10.</span><span class="sxs-lookup"><span data-stu-id="d625c-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="d625c-104">Коэффициент масштабирования определяет количество цифр справа от десятичной запятой. Он находится в диапазоне от 0 до 28.</span><span class="sxs-lookup"><span data-stu-id="d625c-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="d625c-105">С масштабом 0 (без десятичных знаков) максимально возможное значение — +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E + 28).</span><span class="sxs-lookup"><span data-stu-id="d625c-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="d625c-106">С 28 десятичными разрядами максимальное значение — +/-7.9228162514264337593543950335, а наименьшее ненулевое значение — +/-0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="d625c-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="d625c-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d625c-107">Remarks</span></span>

<span data-ttu-id="d625c-108">`Decimal`Тип данных предоставляет наибольшее количество значащих цифр для числа.</span><span class="sxs-lookup"><span data-stu-id="d625c-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="d625c-109">Он поддерживает до 29 значащих цифр и может представлять значения, превышающие 7,9228 x 10 ^ 28.</span><span class="sxs-lookup"><span data-stu-id="d625c-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="d625c-110">Он особенно подходит для вычислений, например финансовых, которые нуждаются в большом количестве цифр, но не могут допускать ошибки округления.</span><span class="sxs-lookup"><span data-stu-id="d625c-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="d625c-111">Значение по умолчанию для типа `Decimal` — 0.</span><span class="sxs-lookup"><span data-stu-id="d625c-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="d625c-112">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="d625c-112">Programming Tips</span></span>

- <span data-ttu-id="d625c-113">**Обеспечивают.**</span><span class="sxs-lookup"><span data-stu-id="d625c-113">**Precision.**</span></span> <span data-ttu-id="d625c-114">`Decimal`не является типом данных с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d625c-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="d625c-115">`Decimal`Структура содержит двоичное целочисленное значение, а также бит знака и целочисленный коэффициент масштабирования, указывающий, какая часть значения является десятичной дробью.</span><span class="sxs-lookup"><span data-stu-id="d625c-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="d625c-116">По этой причине `Decimal` числа имеют более точное представление в памяти, чем типы с плавающей запятой ( `Single` и `Double` ).</span><span class="sxs-lookup"><span data-stu-id="d625c-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="d625c-117">**Производительность.**</span><span class="sxs-lookup"><span data-stu-id="d625c-117">**Performance.**</span></span> <span data-ttu-id="d625c-118">`Decimal`Тип данных является самым медленным из всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="d625c-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="d625c-119">Перед выбором типа данных следует оценить важность точности в соответствии с производительностью.</span><span class="sxs-lookup"><span data-stu-id="d625c-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="d625c-120">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="d625c-120">**Widening.**</span></span> <span data-ttu-id="d625c-121">`Decimal`Тип данных расширяется до `Single` или `Double` .</span><span class="sxs-lookup"><span data-stu-id="d625c-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="d625c-122">Это означает, что можно преобразовать `Decimal` в любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="d625c-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="d625c-123">**Нули в конце.**</span><span class="sxs-lookup"><span data-stu-id="d625c-123">**Trailing Zeros.**</span></span> <span data-ttu-id="d625c-124">Visual Basic не сохраняет конечные нули в `Decimal` литерале.</span><span class="sxs-lookup"><span data-stu-id="d625c-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="d625c-125">Однако `Decimal` переменная сохраняет все конечные нули, полученные при вычислении.</span><span class="sxs-lookup"><span data-stu-id="d625c-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="d625c-126">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d625c-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="d625c-127">Выходные данные `MsgBox` в предыдущем примере имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="d625c-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="d625c-128">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="d625c-128">**Type Characters.**</span></span> <span data-ttu-id="d625c-129">При добавлении к литералу символа типа литерала `D` производится принудительное приведение литерала к типу данных `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d625c-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="d625c-130">При добавлении символа идентификатора типа `@` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d625c-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="d625c-131">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="d625c-131">**Framework Type.**</span></span> <span data-ttu-id="d625c-132">В .NET Framework данный тип соответствует структуре <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d625c-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="d625c-133">Диапазон</span><span class="sxs-lookup"><span data-stu-id="d625c-133">Range</span></span>

 <span data-ttu-id="d625c-134">Может потребоваться использовать `D` символ типа, чтобы присвоить большое значение `Decimal` переменной или константе.</span><span class="sxs-lookup"><span data-stu-id="d625c-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="d625c-135">Это требование обусловлено тем, что компилятор интерпретирует литерал как `Long` , если символ типа литерала не соответствует литералу, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d625c-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="d625c-136">Объявление для `bigDec1` не создает переполнение, так как присваиваемое ему значение попадает в диапазон для `Long` .</span><span class="sxs-lookup"><span data-stu-id="d625c-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="d625c-137">`Long`Значение может быть присвоено `Decimal` переменной.</span><span class="sxs-lookup"><span data-stu-id="d625c-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="d625c-138">Объявление для `bigDec2` создает ошибку переполнения, так как присвоенное ей значение слишком велико для `Long` .</span><span class="sxs-lookup"><span data-stu-id="d625c-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="d625c-139">Поскольку числовой литерал не может быть интерпретирован как `Long` , он не может быть назначен `Decimal` переменной.</span><span class="sxs-lookup"><span data-stu-id="d625c-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="d625c-140">Для `bigDec3` символ типа литерала `D` решает проблему, вызывая компилятору интерпретировать литерал как, `Decimal` а не как `Long` .</span><span class="sxs-lookup"><span data-stu-id="d625c-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d625c-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d625c-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d625c-142">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d625c-142">Data Types</span></span>](index.md)
- [<span data-ttu-id="d625c-143">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="d625c-143">Single Data Type</span></span>](single-data-type.md)
- [<span data-ttu-id="d625c-144">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="d625c-144">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="d625c-145">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="d625c-145">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="d625c-146">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="d625c-146">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="d625c-147">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="d625c-147">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
