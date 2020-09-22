---
title: Предложение Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: f2377d8d1635912885a310b2b0429a6a00083b47
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869670"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="dba87-102">Предложение Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dba87-102">Take Clause (Visual Basic)</span></span>

<span data-ttu-id="dba87-103">Возвращает указанное число идущих подряд элементов с начала коллекции.</span><span class="sxs-lookup"><span data-stu-id="dba87-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba87-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dba87-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="dba87-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="dba87-105">Parts</span></span>  

 `count`  
 <span data-ttu-id="dba87-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dba87-106">Required.</span></span> <span data-ttu-id="dba87-107">Значение или выражение, результатом которого является число возвращаемых элементов последовательности.</span><span class="sxs-lookup"><span data-stu-id="dba87-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba87-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="dba87-108">Remarks</span></span>  

 <span data-ttu-id="dba87-109">`Take`Предложение вызывает включение в запрос указанного числа смежных элементов из начала списка результатов.</span><span class="sxs-lookup"><span data-stu-id="dba87-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="dba87-110">Число включаемых элементов задается `count` параметром.</span><span class="sxs-lookup"><span data-stu-id="dba87-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="dba87-111">`Take`Предложение с `Skip` предложением можно использовать для возврата диапазона данных из любого сегмента запроса.</span><span class="sxs-lookup"><span data-stu-id="dba87-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="dba87-112">Для этого передайте индекс первого элемента диапазона в `Skip` предложение и размер диапазона в `Take` предложение.</span><span class="sxs-lookup"><span data-stu-id="dba87-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="dba87-113">В этом случае `Take` предложение должно быть указано после `Skip` предложения.</span><span class="sxs-lookup"><span data-stu-id="dba87-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="dba87-114">При использовании `Take` предложения в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит `Take` предложению включить предполагаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="dba87-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="dba87-115">Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dba87-115">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="dba87-116">С помощью предложения можно `TakeWhile` указать, что возвращаются только определенные элементы, в зависимости от указанного условия.</span><span class="sxs-lookup"><span data-stu-id="dba87-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dba87-117">Пример</span><span class="sxs-lookup"><span data-stu-id="dba87-117">Example</span></span>  

 <span data-ttu-id="dba87-118">В следующем примере кода предложение используется `Take` вместе с `Skip` предложением для возврата данных из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="dba87-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="dba87-119">Функция "клиенты" использует `Skip` предложение для обхода клиентов в списке до получения значения начального индекса и использует `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="dba87-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="dba87-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dba87-120">See also</span></span>

- <span data-ttu-id="dba87-121">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dba87-121">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="dba87-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="dba87-122">Queries</span></span>](index.md)
- [<span data-ttu-id="dba87-123">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="dba87-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="dba87-124">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="dba87-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="dba87-125">Предложение ORDER BY</span><span class="sxs-lookup"><span data-stu-id="dba87-125">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="dba87-126">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="dba87-126">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="dba87-127">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="dba87-127">Skip Clause</span></span>](skip-clause.md)
