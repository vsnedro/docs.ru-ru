---
title: Предложение Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: af722f7aee021f244b411cdc61619b7de3c20607
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866230"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="ed419-102">Предложение Skip While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed419-102">Skip While Clause (Visual Basic)</span></span>

<span data-ttu-id="ed419-103">Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="ed419-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed419-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed419-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ed419-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="ed419-105">Parts</span></span>  
  
|<span data-ttu-id="ed419-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ed419-106">Term</span></span>|<span data-ttu-id="ed419-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ed419-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="ed419-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ed419-108">Required.</span></span> <span data-ttu-id="ed419-109">Выражение, представляющее условие для проверки элементов.</span><span class="sxs-lookup"><span data-stu-id="ed419-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="ed419-110">Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например, `Integer` для вычисления в виде `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="ed419-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed419-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed419-111">Remarks</span></span>  

 <span data-ttu-id="ed419-112">`Skip While`Предложение обходит элементы из начала результата запроса до тех пор, пока не будут `expression` возвращены `false` .</span><span class="sxs-lookup"><span data-stu-id="ed419-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="ed419-113">После `expression` возврата `false` запрос возвращает все остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="ed419-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="ed419-114">`expression`Для оставшихся результатов игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ed419-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="ed419-115">`Skip While`Предложение отличается от `Where` предложения в том, что `Where` предложение может использоваться для исключения всех элементов из запроса, которые не соответствуют определенному условию.</span><span class="sxs-lookup"><span data-stu-id="ed419-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="ed419-116">`Skip While`Предложение исключает элементы только до первого момента, когда условие не будет удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="ed419-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="ed419-117">`Skip While`Предложение наиболее полезно при работе с упорядоченным результатом запроса.</span><span class="sxs-lookup"><span data-stu-id="ed419-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="ed419-118">Можно обойти определенное количество результатов с начала результата запроса с помощью `Skip` предложения.</span><span class="sxs-lookup"><span data-stu-id="ed419-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed419-119">Пример</span><span class="sxs-lookup"><span data-stu-id="ed419-119">Example</span></span>  

 <span data-ttu-id="ed419-120">В следующем примере кода предложение используется `Skip While` для обхода результатов до тех пор, пока не будет найден первый клиент из США.</span><span class="sxs-lookup"><span data-stu-id="ed419-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ed419-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ed419-121">See also</span></span>

- <span data-ttu-id="ed419-122">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed419-122">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="ed419-123">Запросы</span><span class="sxs-lookup"><span data-stu-id="ed419-123">Queries</span></span>](index.md)
- [<span data-ttu-id="ed419-124">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="ed419-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="ed419-125">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="ed419-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="ed419-126">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="ed419-126">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="ed419-127">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="ed419-127">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="ed419-128">Предложение WHERE</span><span class="sxs-lookup"><span data-stu-id="ed419-128">Where Clause</span></span>](where-clause.md)
