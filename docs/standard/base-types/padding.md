---
title: Заполнение строк в .NET
description: Сведения о том, как заполнять строки в .NET. Используйте методы String.PadLeft и String.PadRight для добавления символов в начале или конце строки, чтобы достигнуть указанной общей длины.
ms.date: 03/15/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
ms.openlocfilehash: 9931db1e76e3737ab3803400928169b30c3ecbda
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822949"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="4085a-104">Заполнение строк в .NET</span><span class="sxs-lookup"><span data-stu-id="4085a-104">Padding Strings in .NET</span></span>

<span data-ttu-id="4085a-105">Перечисленные ниже методы класса <xref:System.String> позволяют создать новую строку, состоящей из исходной строки, и дополнить ее указанными символами с начала или с конца до указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="4085a-105">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="4085a-106">Символом заполнения может быть пробел или указанный знак.</span><span class="sxs-lookup"><span data-stu-id="4085a-106">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="4085a-107">Итоговая строка выравнивается по правому или левому краю.</span><span class="sxs-lookup"><span data-stu-id="4085a-107">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="4085a-108">Если длина исходной строки уже больше или равна требуемой общей длины, методы заполнения возвращают исходную строку без изменений. Дополнительные сведения см. в разделах **Возвращаемые значения** описания двух перегрузок методов <xref:System.String.PadLeft%2A?displayProperty=nameWithType> и <xref:System.String.PadRight%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4085a-108">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="4085a-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="4085a-109">Method name</span></span>|<span data-ttu-id="4085a-110">Использовать</span><span class="sxs-lookup"><span data-stu-id="4085a-110">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="4085a-111">Дополняет строку до указанной общей длины знаками с начала.</span><span class="sxs-lookup"><span data-stu-id="4085a-111">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="4085a-112">Дополняет строку до указанной общей длины знаками с конца.</span><span class="sxs-lookup"><span data-stu-id="4085a-112">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="4085a-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="4085a-113">PadLeft</span></span>  
 <span data-ttu-id="4085a-114">Метод <xref:System.String.PadLeft%2A?displayProperty=nameWithType> создает новую строку, присоединяя в начало исходной строки заполняющие символы в количестве, необходимом для достижения указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="4085a-114">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="4085a-115">Метод <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> в качестве заполняющих символов использует пробелы, а метод <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> позволяет задать любой заполняющий символ.</span><span class="sxs-lookup"><span data-stu-id="4085a-115">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="4085a-116">В следующем примере кода метод <xref:System.String.PadLeft%2A>используется для создания новой строки длиной в двадцать символов.</span><span class="sxs-lookup"><span data-stu-id="4085a-116">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="4085a-117">Этот пример выводит на консоль значение "`--------Hello World!`".</span><span class="sxs-lookup"><span data-stu-id="4085a-117">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="4085a-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="4085a-118">PadRight</span></span>  
 <span data-ttu-id="4085a-119">Метод <xref:System.String.PadRight%2A?displayProperty=nameWithType> создает новую строку, присоединяя в конец исходной строки заполняющие символы в количестве, необходимом для достижения указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="4085a-119">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="4085a-120">Метод <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> в качестве заполняющих символов использует пробелы, а метод <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> позволяет задать любой заполняющий символ.</span><span class="sxs-lookup"><span data-stu-id="4085a-120">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="4085a-121">В следующем примере кода метод <xref:System.String.PadRight%2A>используется для создания новой строки длиной в двадцать символов.</span><span class="sxs-lookup"><span data-stu-id="4085a-121">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="4085a-122">Этот пример выводит на консоль значение "`Hello World!--------`".</span><span class="sxs-lookup"><span data-stu-id="4085a-122">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4085a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4085a-123">See also</span></span>

- [<span data-ttu-id="4085a-124">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4085a-124">Basic String Operations</span></span>](basic-string-operations.md)
