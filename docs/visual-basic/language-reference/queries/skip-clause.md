---
title: Предложение Skip
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 40e89160baf663f7d6785e5d3e09ad6cc4eefbde
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866303"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="193f3-102">Предложение Skip (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="193f3-102">Skip Clause (Visual Basic)</span></span>

<span data-ttu-id="193f3-103">Пропускает заданное число элементов в коллекции и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="193f3-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="193f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="193f3-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="193f3-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="193f3-105">Parts</span></span>  

 `count`  
 <span data-ttu-id="193f3-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="193f3-106">Required.</span></span> <span data-ttu-id="193f3-107">Значение или выражение, результатом которого является число пропускаемых элементов последовательности.</span><span class="sxs-lookup"><span data-stu-id="193f3-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="193f3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="193f3-108">Remarks</span></span>  

 <span data-ttu-id="193f3-109">`Skip`Предложение заставляет запрос обходить элементы в начале списка результатов и возвращать оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="193f3-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="193f3-110">Число пропускаемых элементов определяется `count` параметром.</span><span class="sxs-lookup"><span data-stu-id="193f3-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="193f3-111">`Skip`Предложение с `Take` предложением можно использовать для возврата диапазона данных из любого сегмента запроса.</span><span class="sxs-lookup"><span data-stu-id="193f3-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="193f3-112">Для этого передайте индекс первого элемента диапазона в `Skip` предложение и размер диапазона в `Take` предложение.</span><span class="sxs-lookup"><span data-stu-id="193f3-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="193f3-113">При использовании `Skip` предложения в запросе может также потребоваться убедиться, что результаты возвращаются в порядке, который позволит `Skip` использовать предложение для обхода предполагаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="193f3-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="193f3-114">Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="193f3-114">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="193f3-115">Можно использовать предложение, `SkipWhile` чтобы указать, что игнорируются только определенные элементы, в зависимости от указанного условия.</span><span class="sxs-lookup"><span data-stu-id="193f3-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="193f3-116">Пример</span><span class="sxs-lookup"><span data-stu-id="193f3-116">Example</span></span>  

 <span data-ttu-id="193f3-117">В следующем примере кода предложение используется `Skip` вместе с `Take` предложением для возврата данных из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="193f3-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="193f3-118">`GetCustomers`Функция использует `Skip` предложение для обхода клиентов в списке до получения значения начального индекса и использует `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="193f3-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="193f3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="193f3-119">See also</span></span>

- <span data-ttu-id="193f3-120">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="193f3-120">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="193f3-121">Запросы</span><span class="sxs-lookup"><span data-stu-id="193f3-121">Queries</span></span>](index.md)
- [<span data-ttu-id="193f3-122">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="193f3-122">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="193f3-123">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="193f3-123">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="193f3-124">Предложение ORDER BY</span><span class="sxs-lookup"><span data-stu-id="193f3-124">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="193f3-125">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="193f3-125">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="193f3-126">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="193f3-126">Take Clause</span></span>](take-clause.md)
