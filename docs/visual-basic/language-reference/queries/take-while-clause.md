---
title: Предложение Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 632e9e2195f21a3aa1d1ffd28e9838905c471156
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869661"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="be548-102">Предложение Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be548-102">Take While Clause (Visual Basic)</span></span>

<span data-ttu-id="be548-103">Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="be548-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be548-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be548-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="be548-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="be548-105">Parts</span></span>  
  
|<span data-ttu-id="be548-106">Термин</span><span class="sxs-lookup"><span data-stu-id="be548-106">Term</span></span>|<span data-ttu-id="be548-107">Определение</span><span class="sxs-lookup"><span data-stu-id="be548-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="be548-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="be548-108">Required.</span></span> <span data-ttu-id="be548-109">Выражение, представляющее условие для проверки элементов.</span><span class="sxs-lookup"><span data-stu-id="be548-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="be548-110">Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например, `Integer` для вычисления в виде `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="be548-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be548-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="be548-111">Remarks</span></span>  

 <span data-ttu-id="be548-112">`Take While`Предложение включает элементы из начала результата запроса до тех пор, пока не будут `expression` возвращены `false` .</span><span class="sxs-lookup"><span data-stu-id="be548-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="be548-113">После `expression` возврата `false` запрос будет обходить все оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="be548-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="be548-114">`expression`Для оставшихся результатов игнорируется.</span><span class="sxs-lookup"><span data-stu-id="be548-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="be548-115">`Take While`Предложение отличается от `Where` предложения в том, что `Where` предложение может использоваться для включения всех элементов из запроса, удовлетворяющего определенному условию.</span><span class="sxs-lookup"><span data-stu-id="be548-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="be548-116">`Take While`Предложение включает элементы только до первого момента, когда условие не будет удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="be548-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="be548-117">`Take While`Предложение наиболее полезно при работе с упорядоченным результатом запроса.</span><span class="sxs-lookup"><span data-stu-id="be548-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be548-118">Пример</span><span class="sxs-lookup"><span data-stu-id="be548-118">Example</span></span>  

 <span data-ttu-id="be548-119">В следующем примере кода предложение используется `Take While` для получения результатов до тех пор, пока не будет найден первый клиент без заказов.</span><span class="sxs-lookup"><span data-stu-id="be548-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="be548-120">См. также</span><span class="sxs-lookup"><span data-stu-id="be548-120">See also</span></span>

- <span data-ttu-id="be548-121">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be548-121">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="be548-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="be548-122">Queries</span></span>](index.md)
- [<span data-ttu-id="be548-123">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="be548-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="be548-124">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="be548-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="be548-125">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="be548-125">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="be548-126">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="be548-126">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="be548-127">Предложение WHERE</span><span class="sxs-lookup"><span data-stu-id="be548-127">Where Clause</span></span>](where-clause.md)
