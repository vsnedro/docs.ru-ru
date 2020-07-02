---
title: Пример регулярного выражения. Изменение форматов даты
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: 3b657ac6c88a1ee846f7f1d2156a18fd34621808
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803954"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="61c15-102">Пример регулярного выражения. Изменение форматов даты</span><span class="sxs-lookup"><span data-stu-id="61c15-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="61c15-103">В следующем примере кода метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> используется для замены дат в формате *мм*/*дд*/*гг* на даты в формате *дд*-*мм*-*гг*.</span><span class="sxs-lookup"><span data-stu-id="61c15-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy*.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="61c15-104">Пример</span><span class="sxs-lookup"><span data-stu-id="61c15-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="61c15-105">В следующем коде показано, как можно вызывать метод `MDYToDMY` в приложении.</span><span class="sxs-lookup"><span data-stu-id="61c15-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="61c15-106">Комментарии</span><span class="sxs-lookup"><span data-stu-id="61c15-106">Comments</span></span>  
 <span data-ttu-id="61c15-107">Возможные интерпретации шаблона регулярного выражения `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="61c15-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="61c15-108">Шаблон</span><span class="sxs-lookup"><span data-stu-id="61c15-108">Pattern</span></span>|<span data-ttu-id="61c15-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="61c15-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="61c15-110">Совпадение должно начинаться на границе слова.</span><span class="sxs-lookup"><span data-stu-id="61c15-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="61c15-111">Совпадение с одной или двумя десятичными цифрами.</span><span class="sxs-lookup"><span data-stu-id="61c15-111">Match one or two decimal digits.</span></span> <span data-ttu-id="61c15-112">Это записанная группа `month`.</span><span class="sxs-lookup"><span data-stu-id="61c15-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="61c15-113">Совпадение с косой чертой.</span><span class="sxs-lookup"><span data-stu-id="61c15-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="61c15-114">Совпадение с одной или двумя десятичными цифрами.</span><span class="sxs-lookup"><span data-stu-id="61c15-114">Match one or two decimal digits.</span></span> <span data-ttu-id="61c15-115">Это записанная группа `day`.</span><span class="sxs-lookup"><span data-stu-id="61c15-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="61c15-116">Совпадение с косой чертой.</span><span class="sxs-lookup"><span data-stu-id="61c15-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="61c15-117">Совпадение с двумя-четырьмя десятичными цифрами.</span><span class="sxs-lookup"><span data-stu-id="61c15-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="61c15-118">Это записанная группа `year`.</span><span class="sxs-lookup"><span data-stu-id="61c15-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="61c15-119">Совпадение должно заканчиваться на границе слова.</span><span class="sxs-lookup"><span data-stu-id="61c15-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="61c15-120">Шаблон `${day}-${month}-${year}` определяет строку замены, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="61c15-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="61c15-121">Шаблон</span><span class="sxs-lookup"><span data-stu-id="61c15-121">Pattern</span></span>|<span data-ttu-id="61c15-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="61c15-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="61c15-123">Добавляет строку, которая записана захватываемой группой `day`.</span><span class="sxs-lookup"><span data-stu-id="61c15-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="61c15-124">Добавляет символ дефиса.</span><span class="sxs-lookup"><span data-stu-id="61c15-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="61c15-125">Добавляет строку, которая записана захватываемой группой `month`.</span><span class="sxs-lookup"><span data-stu-id="61c15-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="61c15-126">Добавляет символ дефиса.</span><span class="sxs-lookup"><span data-stu-id="61c15-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="61c15-127">Добавляет строку, которая записана захватываемой группой `year`.</span><span class="sxs-lookup"><span data-stu-id="61c15-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61c15-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61c15-128">See also</span></span>

- [<span data-ttu-id="61c15-129">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="61c15-129">.NET Regular Expressions</span></span>](regular-expressions.md)
