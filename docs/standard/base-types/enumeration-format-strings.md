---
title: Строки форматов перечисления
description: Создавайте строки формата перечисления с помощью метода Enum.ToString в .NET. Форматируйте числовые, шестнадцатеричные или строковые значения членов перечислений.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: 02a12c36e47a82c15c01e578333e1c4465bab142
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829626"
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="cf64e-104">Строки форматов перечисления</span><span class="sxs-lookup"><span data-stu-id="cf64e-104">Enumeration format strings</span></span>

<span data-ttu-id="cf64e-105">Метод <xref:System.Enum.ToString%2A?displayProperty=nameWithType> можно использовать для создания новой строки, представляющей числовое, шестнадцатеричное или строковое значение элемента перечисления.</span><span class="sxs-lookup"><span data-stu-id="cf64e-105">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="cf64e-106">Этот метод принимает строку формата перечисления, чтобы задать возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="cf64e-106">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>

<span data-ttu-id="cf64e-107">В следующей таблице приведены строки форматов перечисления и возвращаемые методом значения.</span><span class="sxs-lookup"><span data-stu-id="cf64e-107">The following sections list the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="cf64e-108">Описатели формата не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="cf64e-108">These format specifiers are not case-sensitive.</span></span>

## <a name="g-or-g"></a><span data-ttu-id="cf64e-109">G или g</span><span class="sxs-lookup"><span data-stu-id="cf64e-109">G or g</span></span>

<span data-ttu-id="cf64e-110">Отображает перечисление в виде строкового значения, если это возможно. В противном случае отображает целочисленное значение текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cf64e-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="cf64e-111">Если для перечисления задан атрибут **Flags**, строковые значения всех допустимых записей объединяются с запятой в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="cf64e-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="cf64e-112">Если атрибут **Flags** не задан, в виде числовой записи отображается недопустимое значение.</span><span class="sxs-lookup"><span data-stu-id="cf64e-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="cf64e-113">В следующем примере показан описатель формата G.</span><span class="sxs-lookup"><span data-stu-id="cf64e-113">The following example illustrates the G format specifier.</span></span>

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a><span data-ttu-id="cf64e-114">F или f</span><span class="sxs-lookup"><span data-stu-id="cf64e-114">F or f</span></span>

<span data-ttu-id="cf64e-115">Отображает перечисление в виде строкового значения, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="cf64e-115">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="cf64e-116">Если перечисление полностью можно отобразить в виде строки как совокупность всех элементов перечисления (даже если атрибут **Flags** не задан), то строковые значения всех действительных записей объединяются с запятой в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="cf64e-116">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="cf64e-117">Если значение не может быть определено по записям перечисления, то значение форматируется аналогично целому типу.</span><span class="sxs-lookup"><span data-stu-id="cf64e-117">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="cf64e-118">В следующем примере показан описатель формата F.</span><span class="sxs-lookup"><span data-stu-id="cf64e-118">The following example illustrates the F format specifier.</span></span>

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a><span data-ttu-id="cf64e-119">D или d</span><span class="sxs-lookup"><span data-stu-id="cf64e-119">D or d</span></span>

<span data-ttu-id="cf64e-120">Отображает запись перечисления в кратчайшем целочисленном представлении.</span><span class="sxs-lookup"><span data-stu-id="cf64e-120">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="cf64e-121">В следующем примере показан описатель формата D.</span><span class="sxs-lookup"><span data-stu-id="cf64e-121">The following example illustrates the D format specifier.</span></span>

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a><span data-ttu-id="cf64e-122">X или x</span><span class="sxs-lookup"><span data-stu-id="cf64e-122">X or x</span></span>

<span data-ttu-id="cf64e-123">Отображает элемент перечисления в виде шестнадцатеричного значения.</span><span class="sxs-lookup"><span data-stu-id="cf64e-123">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="cf64e-124">Значение представлено с обязательным начальным нулем, чтобы обеспечить в строке результата наличие двух символов для каждого байта в [базовом числовом типе](xref:System.Enum.GetUnderlyingType%2A), который принадлежит к типу перечисления.</span><span class="sxs-lookup"><span data-stu-id="cf64e-124">The value is represented with leading zeros as necessary, to ensure that the result string has two characters for each byte in the enumeration type's [underlying numeric type](xref:System.Enum.GetUnderlyingType%2A).</span></span> <span data-ttu-id="cf64e-125">В следующем примере показан описатель формата X.</span><span class="sxs-lookup"><span data-stu-id="cf64e-125">The following example illustrates the X format specifier.</span></span> <span data-ttu-id="cf64e-126">В примере <xref:System.ConsoleColor> и <xref:System.IO.FileAttributes> имеют базовый тип <xref:System.Int32> (32-разрядное (4-байтовое) целое число), который выводит 8-символьную строку результата.</span><span class="sxs-lookup"><span data-stu-id="cf64e-126">In the example, the underlying type of both <xref:System.ConsoleColor> and <xref:System.IO.FileAttributes> is <xref:System.Int32>, or a 32-bit (or 4-byte) integer, which produces an 8-character result string.</span></span>

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a><span data-ttu-id="cf64e-127">Пример</span><span class="sxs-lookup"><span data-stu-id="cf64e-127">Example</span></span>

<span data-ttu-id="cf64e-128">В следующем примере определяется перечисление с именем `Colors`, состоящее из трех элементов: `Red`, `Blue` и `Green`.</span><span class="sxs-lookup"><span data-stu-id="cf64e-128">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

<span data-ttu-id="cf64e-129">После определения перечисления может быть объявлен, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="cf64e-129">After the enumeration is defined, an instance can be declared in the following manner.</span></span>

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

<span data-ttu-id="cf64e-130">Затем метод `Color.ToString(System.String)` можно использовать для отображения значений перечисления различными способами в зависимости от переданного описателя формата.</span><span class="sxs-lookup"><span data-stu-id="cf64e-130">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a><span data-ttu-id="cf64e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="cf64e-131">See also</span></span>

- [<span data-ttu-id="cf64e-132">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="cf64e-132">Formatting Types</span></span>](formatting-types.md)
