---
title: Тип данных Double
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 899554f427ac77ead465752c35e51ca88d045763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415638"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="58a71-102">Тип данных Double (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58a71-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="58a71-103">Содержит подписанные 64-разрядные (8-байтные) числа с плавающей запятой двойной точности, которые находятся в диапазоне от-1.79769313486231570 E + 308 до-4.94065645841246544 E-324 для отрицательных значений и от 4.94065645841246544 E-324 до 1.79769313486231570 E + 308 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="58a71-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="58a71-104">Числа двойной точности хранят приближение вещественного числа.</span><span class="sxs-lookup"><span data-stu-id="58a71-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="58a71-105">Комментарии</span><span class="sxs-lookup"><span data-stu-id="58a71-105">Remarks</span></span>

<span data-ttu-id="58a71-106">`Double`Тип данных предоставляет самые большие и наименьшие возможные величины числа.</span><span class="sxs-lookup"><span data-stu-id="58a71-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="58a71-107">Значение по умолчанию для типа `Double` — 0.</span><span class="sxs-lookup"><span data-stu-id="58a71-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="58a71-108">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="58a71-108">Programming Tips</span></span>

- <span data-ttu-id="58a71-109">**Обеспечивают.**</span><span class="sxs-lookup"><span data-stu-id="58a71-109">**Precision.**</span></span> <span data-ttu-id="58a71-110">При работе с числами с плавающей запятой Помните, что они не всегда имеют точное представление в памяти.</span><span class="sxs-lookup"><span data-stu-id="58a71-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="58a71-111">Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и `Mod` оператор.</span><span class="sxs-lookup"><span data-stu-id="58a71-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="58a71-112">Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="58a71-112">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="58a71-113">**Нули в конце.**</span><span class="sxs-lookup"><span data-stu-id="58a71-113">**Trailing Zeros.**</span></span> <span data-ttu-id="58a71-114">Типы данных с плавающей запятой не имеют внутреннего представления конечных нулей.</span><span class="sxs-lookup"><span data-stu-id="58a71-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="58a71-115">Например, они не различаются между 4,2000 и 4,2.</span><span class="sxs-lookup"><span data-stu-id="58a71-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="58a71-116">Следовательно, конечные нули не отображаются при отображении или печати значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="58a71-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="58a71-117">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="58a71-117">**Type Characters.**</span></span> <span data-ttu-id="58a71-118">При добавлении к литералу символа типа литерала `R` производится принудительное приведение литерала к типу данных `Double`.</span><span class="sxs-lookup"><span data-stu-id="58a71-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="58a71-119">Например, если после целочисленного значения указывается `R` , значение изменяется на `Double` .</span><span class="sxs-lookup"><span data-stu-id="58a71-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="58a71-120">При добавлении символа идентификатора типа `#` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Double`.</span><span class="sxs-lookup"><span data-stu-id="58a71-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="58a71-121">В следующем примере переменная `num` типизирована как `Double` :</span><span class="sxs-lookup"><span data-stu-id="58a71-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="58a71-122">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="58a71-122">**Framework Type.**</span></span> <span data-ttu-id="58a71-123">В .NET Framework данный тип соответствует структуре <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58a71-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="58a71-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="58a71-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="58a71-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="58a71-125">Data Types</span></span>](index.md)
- [<span data-ttu-id="58a71-126">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="58a71-126">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="58a71-127">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="58a71-127">Single Data Type</span></span>](single-data-type.md)
- [<span data-ttu-id="58a71-128">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="58a71-128">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="58a71-129">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="58a71-129">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="58a71-130">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="58a71-130">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="58a71-131">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="58a71-131">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="58a71-132">Символы типов</span><span class="sxs-lookup"><span data-stu-id="58a71-132">Type Characters</span></span>](../../programming-guide/language-features/data-types/type-characters.md)
