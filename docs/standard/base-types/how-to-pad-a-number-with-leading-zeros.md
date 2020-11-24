---
title: Практическое руководство. Дополнение числа начальными нулями
description: Узнайте, как дополнить число начальными нулями. Добавляйте начальные нули к целым числам или числовым значениям до указанной общей длины или добавляйте определенное число начальных нулей.
ms.date: 02/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET]
- formatting [.NET], numbers
- number formatting [.NET]
- numbers [.NET], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: 911d6059d3594ca35eb1c1c3e2d29a5684bce738
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822052"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="38e79-104">Практическое руководство. Дополнение числа начальными нулями</span><span class="sxs-lookup"><span data-stu-id="38e79-104">How to: Pad a Number with Leading Zeros</span></span>

<span data-ttu-id="38e79-105">К целому числу можно добавить начальные нули, используя [строку стандартного числового формата](standard-numeric-format-strings.md) "D" с описателем точности.</span><span class="sxs-lookup"><span data-stu-id="38e79-105">You can add leading zeros to an integer by using the "D" [standard numeric format string](standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="38e79-106">С помощью [строки настраиваемого числового формата](custom-numeric-format-strings.md) начальные нули можно добавлять как к целым числам, так и к числам с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="38e79-106">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](custom-numeric-format-strings.md).</span></span> <span data-ttu-id="38e79-107">В этой статье показано, как использовать оба метода для дополнения числа начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="38e79-107">This article shows how to use both methods to pad a number with leading zeros.</span></span>

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="38e79-108">Дополнение целого числа начальными нулями до определенной длины</span><span class="sxs-lookup"><span data-stu-id="38e79-108">To pad an integer with leading zeros to a specific length</span></span>

1. <span data-ttu-id="38e79-109">Определите минимальное число разрядов для целого числа.</span><span class="sxs-lookup"><span data-stu-id="38e79-109">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="38e79-110">Добавьте к этому значению число начальных разрядов.</span><span class="sxs-lookup"><span data-stu-id="38e79-110">Include any leading digits in this number.</span></span>

1. <span data-ttu-id="38e79-111">Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.</span><span class="sxs-lookup"><span data-stu-id="38e79-111">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="38e79-112">Чтобы показать целое число как десятичное, вызовите метод `ToString(String)` и передайте строку "D *n*" как значение параметра `format`, где *n* представляет минимальную длину строки.</span><span class="sxs-lookup"><span data-stu-id="38e79-112">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D *n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>

    - <span data-ttu-id="38e79-113">Для отображения целого числа в виде шестнадцатеричного значения вызовите его метод `ToString(String)` и передайте строку "X *n*" в качестве значения параметра format, где *n* представляет минимальную длину строки.</span><span class="sxs-lookup"><span data-stu-id="38e79-113">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X *n*" as the value of the format parameter, where *n* represents the minimum length of the string.</span></span>

<span data-ttu-id="38e79-114">Также можно использовать строку формата в интерполированной строке в [C# ](../../csharp/language-reference/tokens/interpolated.md) и [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) или вызвать метод, например <xref:System.String.Format%2A?displayProperty=nameWithType> или <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, который использует [составное форматирование](composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="38e79-114">You can also use the format string in an interpolated string in both [C#](../../csharp/language-reference/tokens/interpolated.md) and [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), or you can call a method, such as <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, that uses [composite formatting](composite-formatting.md).</span></span>

<span data-ttu-id="38e79-115">Следующий пример форматирует несколько целых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов.</span><span class="sxs-lookup"><span data-stu-id="38e79-115">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="38e79-116">Дополнение целого числа определенным количеством начальных нулей</span><span class="sxs-lookup"><span data-stu-id="38e79-116">To pad an integer with a specific number of leading zeros</span></span>

1. <span data-ttu-id="38e79-117">Определите, сколько начальных нулей должно быть в целом числе.</span><span class="sxs-lookup"><span data-stu-id="38e79-117">Determine how many leading zeros you want the integer value to display.</span></span>

1. <span data-ttu-id="38e79-118">Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.</span><span class="sxs-lookup"><span data-stu-id="38e79-118">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="38e79-119">Для форматирования в виде десятичного значения необходимо использовать описатель стандартного формата D.</span><span class="sxs-lookup"><span data-stu-id="38e79-119">Formatting it as a decimal value requires that you use the "D" standard format specifier.</span></span>

    - <span data-ttu-id="38e79-120">Для форматирования в виде шестнадцатеричного значения необходимо использовать описатель стандартного формата X.</span><span class="sxs-lookup"><span data-stu-id="38e79-120">Formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>

1. <span data-ttu-id="38e79-121">Определите длину недополненной числовой строки, вызвав метод `ToString("D").Length` или `ToString("X").Length` целого числа.</span><span class="sxs-lookup"><span data-stu-id="38e79-121">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>

1. <span data-ttu-id="38e79-122">Добавьте число начальных нулей, которое следует добавить в форматированную строку, к длине недополненной числовой строки.</span><span class="sxs-lookup"><span data-stu-id="38e79-122">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="38e79-123">Добавление количества начальных нулей определяет общую длину дополненной строки.</span><span class="sxs-lookup"><span data-stu-id="38e79-123">Adding the number of leading zeros defines the total length of the padded string.</span></span>

1. <span data-ttu-id="38e79-124">Вызовите для целого значения метод `ToString(String)` и передайте строку "D *n*" для десятичных строк или строку "X *n*" для шестнадцатеричных строк, где *n* означает общую длину дополненной строки.</span><span class="sxs-lookup"><span data-stu-id="38e79-124">Call the integer value's `ToString(String)` method, and pass the string "D *n*" for decimal strings and "X *n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="38e79-125">Строку форматирования "D *n*" или "X *n*" можно также использовать в методе, поддерживающем составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="38e79-125">You can also use the "D *n*" or "X *n*" format string in a method that supports composite formatting.</span></span>

<span data-ttu-id="38e79-126">Следующий пример дополняет целое число пятью начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="38e79-126">The following example pads an integer value with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="38e79-127">Дополнение числового значения начальными нулями до определенной длины</span><span class="sxs-lookup"><span data-stu-id="38e79-127">To pad a numeric value with leading zeros to a specific length</span></span>

1. <span data-ttu-id="38e79-128">Определите, сколько разрядов слева от десятичного разделителя должно быть в строковом представлении числа.</span><span class="sxs-lookup"><span data-stu-id="38e79-128">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="38e79-129">Добавьте к этому значению число начальных нулей.</span><span class="sxs-lookup"><span data-stu-id="38e79-129">Include any leading zeros in this total number of digits.</span></span>

1. <span data-ttu-id="38e79-130">Определите строку настраиваемого формата числа, использующую местозаполнитель нуля (0) для представления минимального количества нулей.</span><span class="sxs-lookup"><span data-stu-id="38e79-130">Define a custom numeric format string that uses the zero placeholder "0" to represent the minimum number of zeros.</span></span>

1. <span data-ttu-id="38e79-131">Вызовите метод `ToString(String)` числа и передайте ему строку настраиваемого формата.</span><span class="sxs-lookup"><span data-stu-id="38e79-131">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="38e79-132">Вы также можете использовать строку настраиваемого формата с интерполяцией строки или методом, поддерживающим составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="38e79-132">You can also use the custom format string with string interpolation or with a method that supports composite formatting.</span></span>

<span data-ttu-id="38e79-133">Следующий пример форматирует несколько числовых значений с начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="38e79-133">The following example formats several numeric values with leading zeros.</span></span> <span data-ttu-id="38e79-134">В результате общая длина форматированного числа составляет по крайней мере восемь цифр слева от десятичного разделителя.</span><span class="sxs-lookup"><span data-stu-id="38e79-134">As a result, the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="38e79-135">Дополнение числового значения определенным количеством начальных нулей</span><span class="sxs-lookup"><span data-stu-id="38e79-135">To pad a numeric value with a specific number of leading zeros</span></span>

1. <span data-ttu-id="38e79-136">Определите, сколько начальных нулей должно быть в числовом значении.</span><span class="sxs-lookup"><span data-stu-id="38e79-136">Determine how many leading zeros you want the numeric value to have.</span></span>

1. <span data-ttu-id="38e79-137">Определите количество разрядов слева от десятичного разделителя в недополненной числовой строке:</span><span class="sxs-lookup"><span data-stu-id="38e79-137">Determine the number of digits to the left of the decimal in the unpadded numeric string:</span></span>

    1. <span data-ttu-id="38e79-138">Определите, содержит ли строковое представление числа символ десятичной точки.</span><span class="sxs-lookup"><span data-stu-id="38e79-138">Determine whether the string representation of a number includes a decimal point symbol.</span></span>

    1. <span data-ttu-id="38e79-139">Если это так, определите число символов слева от десятичной точки.</span><span class="sxs-lookup"><span data-stu-id="38e79-139">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>

         <span data-ttu-id="38e79-140">-или-</span><span class="sxs-lookup"><span data-stu-id="38e79-140">-or-</span></span>

         <span data-ttu-id="38e79-141">Если строка не содержит десятичный разделитель, определите длину строки.</span><span class="sxs-lookup"><span data-stu-id="38e79-141">If it doesn't include a decimal point symbol, determine the string's length.</span></span>

1. <span data-ttu-id="38e79-142">Создайте строку настраиваемого формата, которая использует:</span><span class="sxs-lookup"><span data-stu-id="38e79-142">Create a custom format string that uses:</span></span>

    - <span data-ttu-id="38e79-143">Местозаполнитель нуля для каждого начального нуля в строке.</span><span class="sxs-lookup"><span data-stu-id="38e79-143">The zero placeholder "0" for each of the leading zeros to appear in the string.</span></span>

    - <span data-ttu-id="38e79-144">Нулевой местозаполнитель или местозаполнитель разряда # для представления каждого разряда в строке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38e79-144">Either the zero placeholder or the digit placeholder "#" to represent each digit in the default string.</span></span>

1. <span data-ttu-id="38e79-145">Передайте строку настраиваемого формата как параметр методу `ToString(String)` числа или методу, поддерживающему составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="38e79-145">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>

<span data-ttu-id="38e79-146">Следующий пример дополняет два значения типа <xref:System.Double> число пятью начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="38e79-146">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="38e79-147">См. также</span><span class="sxs-lookup"><span data-stu-id="38e79-147">See also</span></span>

- [<span data-ttu-id="38e79-148">Строки настраиваемых числовых форматов</span><span class="sxs-lookup"><span data-stu-id="38e79-148">Custom Numeric Format Strings</span></span>](custom-numeric-format-strings.md)
- [<span data-ttu-id="38e79-149">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="38e79-149">Standard Numeric Format Strings</span></span>](standard-numeric-format-strings.md)
- [<span data-ttu-id="38e79-150">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="38e79-150">Composite Formatting</span></span>](composite-formatting.md)
