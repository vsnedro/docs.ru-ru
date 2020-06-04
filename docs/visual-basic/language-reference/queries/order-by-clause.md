---
title: Предложение Order By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 63f454064e88bc18f252940f3abd8e59b8900e5b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359752"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="bde58-102">Предложение Order By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bde58-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="bde58-103">Задает порядок сортировки для результата запроса.</span><span class="sxs-lookup"><span data-stu-id="bde58-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bde58-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bde58-104">Syntax</span></span>  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="bde58-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="bde58-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="bde58-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="bde58-106">Required.</span></span> <span data-ttu-id="bde58-107">Одно или несколько полей из текущего результата запроса, которые указывают порядок упорядочения возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="bde58-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="bde58-108">Имена полей должны быть разделены запятыми (,).</span><span class="sxs-lookup"><span data-stu-id="bde58-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="bde58-109">Каждое поле можно задать как отсортированное в порядке возрастания или убывания с помощью `Ascending` `Descending` ключевых слов или.</span><span class="sxs-lookup"><span data-stu-id="bde58-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="bde58-110">Если `Ascending` `Descending` ключевое слово or не указано, используется порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="bde58-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="bde58-111">Поля порядка сортировки получают приоритет слева направо.</span><span class="sxs-lookup"><span data-stu-id="bde58-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bde58-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bde58-112">Remarks</span></span>  
 <span data-ttu-id="bde58-113">`Order By`Для сортировки результатов запроса можно использовать предложение.</span><span class="sxs-lookup"><span data-stu-id="bde58-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="bde58-114">`Order By`Предложение может сортировать результат только на основе переменной диапазона для текущей области.</span><span class="sxs-lookup"><span data-stu-id="bde58-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="bde58-115">Например, `Select` предложение вводит новую область в выражении запроса с новыми переменными итерации для этой области.</span><span class="sxs-lookup"><span data-stu-id="bde58-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="bde58-116">Переменные диапазона, определенные перед `Select` предложением в запросе, недоступны после `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="bde58-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="bde58-117">Поэтому, если требуется упорядочить результаты по полю, которое недоступно в `Select` предложении, необходимо поместить `Order By` предложение перед `Select` предложением.</span><span class="sxs-lookup"><span data-stu-id="bde58-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="bde58-118">Одним из примеров того, когда это потребуется, является то, что нужно отсортировать запрос по полям, которые не возвращаются как часть результата.</span><span class="sxs-lookup"><span data-stu-id="bde58-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="bde58-119">Порядок сортировки для поля по возрастанию и убыванию определяется реализацией <xref:System.IComparable> интерфейса для типа данных поля.</span><span class="sxs-lookup"><span data-stu-id="bde58-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="bde58-120">Если тип данных не реализует <xref:System.IComparable> интерфейс, порядок сортировки игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bde58-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bde58-121">Пример</span><span class="sxs-lookup"><span data-stu-id="bde58-121">Example</span></span>  
 <span data-ttu-id="bde58-122">Следующее выражение запроса использует `From` предложение для объявления переменной диапазона `book` для `books` коллекции.</span><span class="sxs-lookup"><span data-stu-id="bde58-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="bde58-123">`Order By`Предложение сортирует результат запроса по цене в возрастающем порядке (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bde58-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="bde58-124">Книги с одинаковой ценой сортируются по названию в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="bde58-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="bde58-125">`Select`Предложение выбирает `Title` Свойства и в `Price` качестве значений, возвращаемых запросом.</span><span class="sxs-lookup"><span data-stu-id="bde58-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="bde58-126">Пример</span><span class="sxs-lookup"><span data-stu-id="bde58-126">Example</span></span>  
 <span data-ttu-id="bde58-127">Следующее выражение запроса использует `Order By` предложение для сортировки результата запроса по цене в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="bde58-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="bde58-128">Книги с одинаковой ценой сортируются по названию в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="bde58-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="bde58-129">Пример</span><span class="sxs-lookup"><span data-stu-id="bde58-129">Example</span></span>  
 <span data-ttu-id="bde58-130">Следующее выражение запроса использует `Select` предложение для выбора названия книги, цены, даты публикации и автора.</span><span class="sxs-lookup"><span data-stu-id="bde58-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="bde58-131">Затем он заполняет `Title` `Price` поля,, `PublishDate` и `Author` переменной диапазона для новой области.</span><span class="sxs-lookup"><span data-stu-id="bde58-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="bde58-132">`Order By`Предложение упорядочивает новую переменную диапазона по имени автора, названию книги и стоимости.</span><span class="sxs-lookup"><span data-stu-id="bde58-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="bde58-133">Каждый столбец сортируется в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="bde58-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="bde58-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bde58-134">See also</span></span>

- <span data-ttu-id="bde58-135">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bde58-135">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="bde58-136">Запросы</span><span class="sxs-lookup"><span data-stu-id="bde58-136">Queries</span></span>](index.md)
- [<span data-ttu-id="bde58-137">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="bde58-137">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="bde58-138">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="bde58-138">From Clause</span></span>](from-clause.md)
