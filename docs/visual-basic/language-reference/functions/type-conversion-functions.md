---
title: Type Conversion Functions
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: 5c0cfae01da02222d0827e81ec1ed35ce353ead1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415379"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="1711c-102">Функции преобразования типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1711c-102">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="1711c-103">Эти функции компилируются встроенным, то есть код преобразования является частью кода, который вычисляет выражение.</span><span class="sxs-lookup"><span data-stu-id="1711c-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="1711c-104">Иногда нет вызова процедуры для выполнения преобразования, что повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="1711c-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="1711c-105">Каждая функция приводит выражение к определенному типу данных.</span><span class="sxs-lookup"><span data-stu-id="1711c-105">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="1711c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1711c-106">Syntax</span></span>

```vb
CBool(expression)
CByte(expression)
CChar(expression)
CDate(expression)
CDbl(expression)
CDec(expression)
CInt(expression)
CLng(expression)
CObj(expression)
CSByte(expression)
CShort(expression)
CSng(expression)
CStr(expression)
CUInt(expression)
CULng(expression)
CUShort(expression)
```

## <a name="part"></a><span data-ttu-id="1711c-107">Часть</span><span class="sxs-lookup"><span data-stu-id="1711c-107">Part</span></span>

`expression`  
<span data-ttu-id="1711c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1711c-108">Required.</span></span> <span data-ttu-id="1711c-109">Любое выражение исходного типа данных.</span><span class="sxs-lookup"><span data-stu-id="1711c-109">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="1711c-110">Тип данных возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="1711c-110">Return Value Data Type</span></span>

<span data-ttu-id="1711c-111">Имя функции определяет тип данных возвращаемого значения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1711c-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="1711c-112">Имя функции</span><span class="sxs-lookup"><span data-stu-id="1711c-112">Function name</span></span>|<span data-ttu-id="1711c-113">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="1711c-113">Return data type</span></span>|<span data-ttu-id="1711c-114">Диапазон для `expression` аргумента</span><span class="sxs-lookup"><span data-stu-id="1711c-114">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="1711c-115">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="1711c-115">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="1711c-116">Любое допустимое `Char` или `String` числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="1711c-116">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="1711c-117">Тип данных Byte</span><span class="sxs-lookup"><span data-stu-id="1711c-117">Byte Data Type</span></span>](../data-types/byte-data-type.md)|<span data-ttu-id="1711c-118"><xref:System.Byte.MinValue?displayProperty=nameWithType>(от 0) до <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (без знака); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-119">Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в байтовую `CByte` функцию. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-120">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-120">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="1711c-121">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="1711c-121">Char Data Type</span></span>](../data-types/char-data-type.md)|<span data-ttu-id="1711c-122">Любое допустимое `Char` `String` выражение или; преобразуется только первый символ `String` ; значение может быть от 0 до 65535 (без знака).</span><span class="sxs-lookup"><span data-stu-id="1711c-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="1711c-123">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="1711c-123">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="1711c-124">Любое допустимое представление даты и времени.</span><span class="sxs-lookup"><span data-stu-id="1711c-124">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="1711c-125">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="1711c-125">Double Data Type</span></span>](../data-types/double-data-type.md)|<span data-ttu-id="1711c-126">-1.79769313486231570 e + 308 до-4.94065645841246544 E-324 для отрицательных значений; 4.94065645841246544 e-324 до 1.79769313486231570 E + 308 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="1711c-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="1711c-127">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="1711c-127">Decimal Data Type</span></span>](../data-types/decimal-data-type.md)|<span data-ttu-id="1711c-128">+/-79,228,162,514,264,337,593,543,950,335 для чисел с нулевым масштабом, то есть чисел без десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="1711c-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="1711c-129">Для чисел с 28 десятичными разрядами диапазоном является +/-7.9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="1711c-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="1711c-130">Наименьшее возможное ненулевое число — 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="1711c-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="1711c-131">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="1711c-131">Integer Data Type</span></span>](../data-types/integer-data-type.md)|<span data-ttu-id="1711c-132"><xref:System.Int32.MinValue?displayProperty=nameWithType>(от-2 147 483 648) до <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2 147 483 647); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="1711c-133">Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в целое с помощью `CInt` функции. Дополнительные сведения см. в разделе ["Примечания](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="1711c-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-134">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-134">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="1711c-135">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="1711c-135">Long Data Type</span></span>](../data-types/long-data-type.md)|<span data-ttu-id="1711c-136"><xref:System.Int64.MinValue?displayProperty=nameWithType>(от-9223372036854775808) до <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9 223 372 036 854 775 807); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-137">Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в 64-разрядное целое число с помощью `CLng` функции; Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-138">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-138">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="1711c-139">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="1711c-139">Object Data Type</span></span>](../data-types/object-data-type.md)|<span data-ttu-id="1711c-140">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="1711c-140">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="1711c-141">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="1711c-141">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)|<span data-ttu-id="1711c-142"><xref:System.SByte.MinValue?displayProperty=nameWithType>(от-128) до <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-143">Начиная с Visual Basic 15,8, Visual Basic оптимизирует производительность преобразования байтов с плавающей запятой в функцию с помощью `CSByte` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-144">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-144">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="1711c-145">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="1711c-145">Short Data Type</span></span>](../data-types/short-data-type.md)|<span data-ttu-id="1711c-146"><xref:System.Int16.MinValue?displayProperty=nameWithType>(от-32 768) до <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32 767); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-147">Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в 16-разрядное целое с помощью `CShort` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-148">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-148">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="1711c-149">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="1711c-149">Single Data Type</span></span>](../data-types/single-data-type.md)|<span data-ttu-id="1711c-150">-3.402823 e + 38 – 1.401298 E-45 для отрицательных значений; 1.401298 e-45 до 3.402823 E + 38 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="1711c-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="1711c-151">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="1711c-151">String Data Type</span></span>](../data-types/string-data-type.md)|<span data-ttu-id="1711c-152">Для `CStr` зависит от `expression` аргумента.</span><span class="sxs-lookup"><span data-stu-id="1711c-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="1711c-153">См. раздел [возвращаемые значения для функции CStr](return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="1711c-153">See [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="1711c-154">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="1711c-154">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)|<span data-ttu-id="1711c-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType>(от 0) до <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4 294 967 295) (без знака); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-156">Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в целое число без знака с помощью `CUInt` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-157">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-157">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="1711c-158">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="1711c-158">ULong Data Type</span></span>](../data-types/ulong-data-type.md)|<span data-ttu-id="1711c-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType>(от 0) до <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (без знака); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-160">Начиная с Visual Basic 15,8, Visual Basic оптимизирует производительность преобразования с плавающей запятой в функцию длинного целого числа без знака с помощью `CULng` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-161">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-161">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="1711c-162">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="1711c-162">UShort Data Type</span></span>](../data-types/ushort-data-type.md)|<span data-ttu-id="1711c-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType>(от 0) до <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65 535) (без знака); дробные части округляются.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="1711c-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="1711c-164">Начиная с Visual Basic 15,8, Visual Basic оптимизирует производительность преобразования 16-разрядного целого числа без знака с плавающей запятой в `CUShort` функцию. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1711c-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="1711c-165">Пример см. в разделе пример для функции [CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="1711c-165">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="1711c-166"><sup>1</sup> дробная часть может подвергаться специальному типу округления, называемому *банковским округлением*.</span><span class="sxs-lookup"><span data-stu-id="1711c-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="1711c-167">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="1711c-167">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="1711c-168">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1711c-168">Remarks</span></span>

<span data-ttu-id="1711c-169">Как правило, следует использовать функции преобразования типа Visual Basic в качестве предпочтений для методов .NET Framework, таких как `ToString()` , в <xref:System.Convert> классе или в отдельной структуре типа или классе.</span><span class="sxs-lookup"><span data-stu-id="1711c-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="1711c-170">Функции Visual Basic предназначены для оптимального взаимодействия с Visual Basicным кодом, а также для сокращения исходного кода и упрощения его чтения.</span><span class="sxs-lookup"><span data-stu-id="1711c-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="1711c-171">Кроме того, методы преобразования .NET Framework не всегда дают те же результаты, что и функции Visual Basic, например при преобразовании `Boolean` в `Integer` .</span><span class="sxs-lookup"><span data-stu-id="1711c-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="1711c-172">Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1711c-172">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="1711c-173">Начиная с Visual Basic 15,8, производительность преобразования с плавающей запятой в целое число оптимизируется при передаче <xref:System.Single> значения или, <xref:System.Double> возвращаемого следующими методами, в одну из целочисленных функций преобразования (,,,,,, `CByte` `CShort` `CInt` `CLng` `CSByte` `CUShort` `CUInt` , `CULng` ):</span><span class="sxs-lookup"><span data-stu-id="1711c-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="1711c-174">Такая оптимизация позволяет выполнять код, выполняющий большое количество целочисленных преобразований, в два раза быстрее.</span><span class="sxs-lookup"><span data-stu-id="1711c-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="1711c-175">В следующем примере демонстрируются эти оптимизированные преобразования с плавающей запятой в целые числа:</span><span class="sxs-lookup"><span data-stu-id="1711c-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="1711c-176">Поведение</span><span class="sxs-lookup"><span data-stu-id="1711c-176">Behavior</span></span>

- <span data-ttu-id="1711c-177">**Приведение.**</span><span class="sxs-lookup"><span data-stu-id="1711c-177">**Coercion.**</span></span> <span data-ttu-id="1711c-178">В общем случае можно использовать функции преобразования типов данных для приведения результата операции к конкретному типу данных, а не по типу данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1711c-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="1711c-179">Например, используйте `CDec` для принудительного выполнения десятичных арифметических операций в случаях, когда обычно выполняется операция с одиночной точностью, двойной точностью или целочисленной.</span><span class="sxs-lookup"><span data-stu-id="1711c-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="1711c-180">**Неудачные преобразования.**</span><span class="sxs-lookup"><span data-stu-id="1711c-180">**Failed Conversions.**</span></span> <span data-ttu-id="1711c-181">Если `expression` переданный функции объект находится вне диапазона типа данных, в который она должна быть преобразована, <xref:System.OverflowException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="1711c-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="1711c-182">**Дробные части.**</span><span class="sxs-lookup"><span data-stu-id="1711c-182">**Fractional Parts.**</span></span> <span data-ttu-id="1711c-183">При преобразовании нецелочисленного значения в целочисленные функции целочисленного преобразования ( `CByte` , `CInt` ,,, `CLng` , `CSByte` `CShort` `CUInt` , `CULng` и `CUShort` ) удаляют дробную часть и округляют значение до ближайшего целого.</span><span class="sxs-lookup"><span data-stu-id="1711c-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="1711c-184">Если дробная часть равна точности 0,5, функции целочисленного преобразования округляют его до ближайшего четного целого числа.</span><span class="sxs-lookup"><span data-stu-id="1711c-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="1711c-185">Например, 0,5 округляется до 0, а 1,5 и 2,5 оба округляются в 2.</span><span class="sxs-lookup"><span data-stu-id="1711c-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="1711c-186">Иногда это называется *округлением банка*и предназначено для компенсации смещения, которое может накапливаться при одновременном добавлении многих таких чисел.</span><span class="sxs-lookup"><span data-stu-id="1711c-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="1711c-187">`CInt`и `CLng` отличаются от <xref:Microsoft.VisualBasic.Conversion.Int%2A> функций и <xref:Microsoft.VisualBasic.Conversion.Fix%2A> , которые усекаются, а не округляют дробную часть числа.</span><span class="sxs-lookup"><span data-stu-id="1711c-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="1711c-188">Кроме того, `Fix` и `Int` всегда возвращают значение того же типа данных, что и при передаче.</span><span class="sxs-lookup"><span data-stu-id="1711c-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="1711c-189">**Преобразования даты и времени.**</span><span class="sxs-lookup"><span data-stu-id="1711c-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="1711c-190">Используйте <xref:Microsoft.VisualBasic.Information.IsDate%2A> функцию, чтобы определить, можно ли преобразовать значение в дату и время.</span><span class="sxs-lookup"><span data-stu-id="1711c-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="1711c-191">`CDate`распознает литералы даты и литералы времени, но не числовые значения.</span><span class="sxs-lookup"><span data-stu-id="1711c-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="1711c-192">Чтобы преобразовать значение Visual Basic 6,0 в `Date` `Date` значение в Visual Basic 2005 или более поздней версии, можно использовать <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="1711c-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="1711c-193">**Нейтральные значения даты и времени.**</span><span class="sxs-lookup"><span data-stu-id="1711c-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="1711c-194">[Тип данных Date](../data-types/date-data-type.md) всегда содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="1711c-194">The [Date Data Type](../data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="1711c-195">В целях преобразования типов Visual Basic учитывает 1/1/0001 (1 января 1 года) как *нейтральное значение* для даты, а 00:00:00 (полночь) — как нейтральное значение времени.</span><span class="sxs-lookup"><span data-stu-id="1711c-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="1711c-196">При преобразовании `Date` значения в строку не `CStr` включает нейтральные значения в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="1711c-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="1711c-197">Например, если преобразовать `#January 1, 0001 9:30:00#` в строку, то результатом будет "9:30:00 AM"; сведения о дате подавляются.</span><span class="sxs-lookup"><span data-stu-id="1711c-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="1711c-198">Однако сведения о дате по-прежнему содержатся в исходном `Date` значении и могут быть восстановлены с помощью таких функций, как <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Function.</span><span class="sxs-lookup"><span data-stu-id="1711c-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="1711c-199">**Чувствительность языка и региональных параметров.**</span><span class="sxs-lookup"><span data-stu-id="1711c-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="1711c-200">Функции преобразования типов, включающие строки, выполняют преобразования в соответствии с текущими параметрами языка и региональных параметров для приложения.</span><span class="sxs-lookup"><span data-stu-id="1711c-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="1711c-201">Например, `CDate` распознает форматы даты в соответствии с настройками языкового стандарта системы.</span><span class="sxs-lookup"><span data-stu-id="1711c-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="1711c-202">Необходимо указать день, месяц и год в правильном порядке для вашего языкового стандарта, иначе Дата может интерпретироваться неправильно.</span><span class="sxs-lookup"><span data-stu-id="1711c-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="1711c-203">Длинный формат даты не распознается, если он содержит строку дня недели, например "среда".</span><span class="sxs-lookup"><span data-stu-id="1711c-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="1711c-204">Если необходимо преобразовать в строковое представление значения или из него в формате, отличном от указанного в Вашем языковом стандарте, то нельзя использовать функции преобразования типа Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1711c-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="1711c-205">Для этого используйте `ToString(IFormatProvider)` `Parse(String, IFormatProvider)` методы и типа этого значения.</span><span class="sxs-lookup"><span data-stu-id="1711c-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="1711c-206">Например, используйте <xref:System.Double.Parse%2A?displayProperty=nameWithType> при преобразовании строки в `Double` и используйте <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в строку.</span><span class="sxs-lookup"><span data-stu-id="1711c-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="1711c-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="1711c-207">CType Function</span></span>

<span data-ttu-id="1711c-208">[Функция CType](ctype-function.md) принимает второй аргумент, `typename` и `expression` `typename` `typename` применяет к, где может быть любым типом данных, структурой, классом или интерфейсом, к которому существует допустимое преобразование.</span><span class="sxs-lookup"><span data-stu-id="1711c-208">The [CType Function](ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="1711c-209">Сравнение `CType` с другими ключевыми словами преобразования типов см. в разделе Оператор [DirectCast](../operators/directcast-operator.md) и [Оператор TryCast](../operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1711c-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../operators/directcast-operator.md) and [TryCast Operator](../operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="1711c-210">Пример CBool</span><span class="sxs-lookup"><span data-stu-id="1711c-210">CBool Example</span></span>

<span data-ttu-id="1711c-211">В следующем примере функция используется `CBool` для преобразования выражений в `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="1711c-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="1711c-212">Если результат выражения равен ненулевому значению, `CBool` `True` функция возвращает; в противном случае возвращается значение `False` .</span><span class="sxs-lookup"><span data-stu-id="1711c-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="1711c-213">Пример CByte</span><span class="sxs-lookup"><span data-stu-id="1711c-213">CByte Example</span></span>

<span data-ttu-id="1711c-214">В следующем примере функция используется `CByte` для преобразования выражения в `Byte` .</span><span class="sxs-lookup"><span data-stu-id="1711c-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="1711c-215">Пример CChar</span><span class="sxs-lookup"><span data-stu-id="1711c-215">CChar Example</span></span>

<span data-ttu-id="1711c-216">В следующем примере функция используется `CChar` для преобразования первого символа `String` выражения в `Char` тип.</span><span class="sxs-lookup"><span data-stu-id="1711c-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="1711c-217">Входной аргумент `CChar` должен иметь тип данных `Char` или `String` .</span><span class="sxs-lookup"><span data-stu-id="1711c-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="1711c-218">Нельзя использовать `CChar` для преобразования числа в символ, поскольку `CChar` не может принимать числовые типы данных.</span><span class="sxs-lookup"><span data-stu-id="1711c-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="1711c-219">В следующем примере получается число, представляющее кодовую точку (код символа), и преобразуется в соответствующий символ.</span><span class="sxs-lookup"><span data-stu-id="1711c-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="1711c-220">Она использует <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> функцию для получения строки разрядов, `CInt` преобразования строки в тип `Integer` и `ChrW` для преобразования числа в тип `Char` .</span><span class="sxs-lookup"><span data-stu-id="1711c-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="1711c-221">Пример для CDate</span><span class="sxs-lookup"><span data-stu-id="1711c-221">CDate Example</span></span>

<span data-ttu-id="1711c-222">В следующем примере функция используется `CDate` для преобразования строк в `Date` значения.</span><span class="sxs-lookup"><span data-stu-id="1711c-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="1711c-223">Обычно не рекомендуется жестко кодировать даты и время в виде строк (как показано в этом примере).</span><span class="sxs-lookup"><span data-stu-id="1711c-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="1711c-224">Вместо этого используйте литералы даты и временные литералы, например #Feb 12, 1969 # и #4:45:23 PM #.</span><span class="sxs-lookup"><span data-stu-id="1711c-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="1711c-225">Пример с CDbl</span><span class="sxs-lookup"><span data-stu-id="1711c-225">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="1711c-226">Пример CDec</span><span class="sxs-lookup"><span data-stu-id="1711c-226">CDec Example</span></span>

<span data-ttu-id="1711c-227">В следующем примере функция используется `CDec` для преобразования числового значения в `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="1711c-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="1711c-228">Пример функции CInt</span><span class="sxs-lookup"><span data-stu-id="1711c-228">CInt Example</span></span>

<span data-ttu-id="1711c-229">В следующем примере функция используется `CInt` для преобразования значения в `Integer` .</span><span class="sxs-lookup"><span data-stu-id="1711c-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="1711c-230">Пример с CLng</span><span class="sxs-lookup"><span data-stu-id="1711c-230">CLng Example</span></span>

<span data-ttu-id="1711c-231">В следующем примере функция используется `CLng` для преобразования значений в `Long` .</span><span class="sxs-lookup"><span data-stu-id="1711c-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="1711c-232">Пример CObj</span><span class="sxs-lookup"><span data-stu-id="1711c-232">CObj Example</span></span>

<span data-ttu-id="1711c-233">В следующем примере функция используется `CObj` для преобразования числового значения в `Object` .</span><span class="sxs-lookup"><span data-stu-id="1711c-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="1711c-234">`Object`Сама переменная содержит только 4-байтовый указатель, указывающий на `Double` присвоенное ему значение.</span><span class="sxs-lookup"><span data-stu-id="1711c-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="1711c-235">Пример Ксбите</span><span class="sxs-lookup"><span data-stu-id="1711c-235">CSByte Example</span></span>

<span data-ttu-id="1711c-236">В следующем примере функция используется `CSByte` для преобразования числового значения в `SByte` .</span><span class="sxs-lookup"><span data-stu-id="1711c-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="1711c-237">Пример CShort</span><span class="sxs-lookup"><span data-stu-id="1711c-237">CShort Example</span></span>

<span data-ttu-id="1711c-238">В следующем примере функция используется `CShort` для преобразования числового значения в `Short` .</span><span class="sxs-lookup"><span data-stu-id="1711c-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="1711c-239">Пример CSng</span><span class="sxs-lookup"><span data-stu-id="1711c-239">CSng Example</span></span>

<span data-ttu-id="1711c-240">В следующем примере функция используется `CSng` для преобразования значений в `Single` .</span><span class="sxs-lookup"><span data-stu-id="1711c-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="1711c-241">Пример функции CStr</span><span class="sxs-lookup"><span data-stu-id="1711c-241">CStr Example</span></span>

<span data-ttu-id="1711c-242">В следующем примере функция используется `CStr` для преобразования числового значения в `String` .</span><span class="sxs-lookup"><span data-stu-id="1711c-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="1711c-243">В следующем примере функция используется `CStr` для преобразования `Date` значений в `String` значения.</span><span class="sxs-lookup"><span data-stu-id="1711c-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="1711c-244">`CStr`всегда отображает `Date` значение в стандартном коротком формате для текущего языкового стандарта, например "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="1711c-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="1711c-245">Однако `CStr` подавляет *нейтральные значения* 1/1/0001 для даты и 00:00:00 для времени.</span><span class="sxs-lookup"><span data-stu-id="1711c-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="1711c-246">Дополнительные сведения о значениях, возвращаемых `CStr` , см. в разделе [возвращаемые значения функции CStr](return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="1711c-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="1711c-247">Пример Куинт</span><span class="sxs-lookup"><span data-stu-id="1711c-247">CUInt Example</span></span>

<span data-ttu-id="1711c-248">В следующем примере функция используется `CUInt` для преобразования числового значения в `UInteger` .</span><span class="sxs-lookup"><span data-stu-id="1711c-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="1711c-249">Пример Кулнг</span><span class="sxs-lookup"><span data-stu-id="1711c-249">CULng Example</span></span>

<span data-ttu-id="1711c-250">В следующем примере функция используется `CULng` для преобразования числового значения в `ULong` .</span><span class="sxs-lookup"><span data-stu-id="1711c-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="1711c-251">Пример Кушорт</span><span class="sxs-lookup"><span data-stu-id="1711c-251">CUShort Example</span></span>

<span data-ttu-id="1711c-252">В следующем примере функция используется `CUShort` для преобразования числового значения в `UShort` .</span><span class="sxs-lookup"><span data-stu-id="1711c-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="1711c-253">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1711c-253">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="1711c-254">Функции преобразования</span><span class="sxs-lookup"><span data-stu-id="1711c-254">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="1711c-255">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1711c-255">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
