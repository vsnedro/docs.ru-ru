---
title: Операции, использующие квантификаторы (C#)
description: Узнайте об операциях квантификатора. Эти операции возвращают логическое значение, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: ce06f887d3ad7b10cbdedf9e33072df2c0819ef1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299153"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="36657-104">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="36657-104">Quantifier Operations (C#)</span></span>
<span data-ttu-id="36657-105">Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="36657-105">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="36657-106">На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям.</span><span class="sxs-lookup"><span data-stu-id="36657-106">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="36657-107">Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="36657-107">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="36657-108">Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="36657-108">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Операции, использующие квантификаторы LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="36657-110">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.</span><span class="sxs-lookup"><span data-stu-id="36657-110">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36657-111">Методы</span><span class="sxs-lookup"><span data-stu-id="36657-111">Methods</span></span>  
  
|<span data-ttu-id="36657-112">Имя метода</span><span class="sxs-lookup"><span data-stu-id="36657-112">Method Name</span></span>|<span data-ttu-id="36657-113">Описание</span><span class="sxs-lookup"><span data-stu-id="36657-113">Description</span></span>|<span data-ttu-id="36657-114">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="36657-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="36657-115">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="36657-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="36657-116">Все</span><span class="sxs-lookup"><span data-stu-id="36657-116">All</span></span>|<span data-ttu-id="36657-117">Определяет, все ли элементы последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="36657-117">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="36657-118">Не применяется</span><span class="sxs-lookup"><span data-stu-id="36657-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="36657-119">Любой</span><span class="sxs-lookup"><span data-stu-id="36657-119">Any</span></span>|<span data-ttu-id="36657-120">Определяет, удовлетворяют ли условию какие-либо элементы последовательности.</span><span class="sxs-lookup"><span data-stu-id="36657-120">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="36657-121">Не применяется</span><span class="sxs-lookup"><span data-stu-id="36657-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="36657-122">Содержит</span><span class="sxs-lookup"><span data-stu-id="36657-122">Contains</span></span>|<span data-ttu-id="36657-123">Определяет, содержит ли последовательность указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="36657-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="36657-124">Не применяется</span><span class="sxs-lookup"><span data-stu-id="36657-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="36657-125">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="36657-125">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="36657-126">Все</span><span class="sxs-lookup"><span data-stu-id="36657-126">All</span></span>  
<span data-ttu-id="36657-127">В следующем примере используется `All` для проверки того, что все строки имеют определенную длину.</span><span class="sxs-lookup"><span data-stu-id="36657-127">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="36657-128">Любой</span><span class="sxs-lookup"><span data-stu-id="36657-128">Any</span></span>  
<span data-ttu-id="36657-129">В следующем примере используется `Any` для проверки того, что все строки начинаются o.</span><span class="sxs-lookup"><span data-stu-id="36657-129">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="36657-130">Содержит</span><span class="sxs-lookup"><span data-stu-id="36657-130">Contains</span></span>  
<span data-ttu-id="36657-131">В следующем примере используется `Contains` для проверки того, что массив имеет указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="36657-131">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="36657-132">См. также</span><span class="sxs-lookup"><span data-stu-id="36657-132">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="36657-133">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="36657-133">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="36657-134">Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="36657-134">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="36657-135">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="36657-135">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
