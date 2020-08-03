---
title: Операции Join (C#)
description: Соединение двух источников данных — это связь объектов с объектами, которые имеют общий атрибут в разных источниках данных. Узнайте о методах соединения в среде LINQ в C#.
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 1b453f1752edf0cc126f8e27dbdd9e91ad9143f3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165698"
---
# <a name="no-locjoin-operations-c"></a><span data-ttu-id="9a470-104">Операции Join (C#)</span><span class="sxs-lookup"><span data-stu-id="9a470-104">Join Operations (C#)</span></span>

<span data-ttu-id="9a470-105">*Соединение* двух источников данных — это связь объектов в одном источнике данных с объектами, которые имеют общий атрибут в другом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="9a470-105">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="9a470-106">Join является важной операцией в запросах, направленных на источники данных, отношения которых друг к другу нельзя отследить напрямую.</span><span class="sxs-lookup"><span data-stu-id="9a470-106">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="9a470-107">В объектно-ориентированном программировании оно может означать корреляцию между немоделируемыми объектами, например такими, как обратное направление одностороннего отношения.</span><span class="sxs-lookup"><span data-stu-id="9a470-107">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="9a470-108">Примером одностороннего отношения является класс Customer, имеющий свойство типа City (город), в то время как класс City не имеет свойства, которое является коллекцией объектов Customer (клиент).</span><span class="sxs-lookup"><span data-stu-id="9a470-108">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="9a470-109">В случае наличия списка объектов City для поиска всех клиентов в каждом городе можно использовать операцию соединения.</span><span class="sxs-lookup"><span data-stu-id="9a470-109">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="9a470-110">На платформе LINQ представлены методы объединения <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a470-110">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="9a470-111">Они выполняют эквисоединения, или соединения, которые сопоставляют два источника данных на основе равенства их ключей.</span><span class="sxs-lookup"><span data-stu-id="9a470-111">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="9a470-112">(Для сравнения, Transact-SQL поддерживает операции соединения, отличные от оператора "равно", например оператор "меньше, чем".) В терминах реляционных баз данных <xref:System.Linq.Enumerable.Join%2A> реализует внутреннее соединение — тип соединения, в котором возвращаются только те объекты, у которых есть совпадения в другом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="9a470-112">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="9a470-113">Метод <xref:System.Linq.Enumerable.GroupJoin%2A> не имеет прямого эквивалента в терминах реляционных баз данных, но реализует надмножество внутренних соединений и левых внешних соединений.</span><span class="sxs-lookup"><span data-stu-id="9a470-113">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="9a470-114">Левое внешнее соединение — это соединение, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="9a470-114">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="9a470-115">На следующем рисунке показано концептуальное представление из двух наборов и элементов, входящих в эти наборы, которые включены либо во внутреннее соединение, либо в левое внешнее соединение.</span><span class="sxs-lookup"><span data-stu-id="9a470-115">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Два перекрывающихся кольца, отображающие внешнее&#47;внутреннее соединение.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="9a470-117">Методы</span><span class="sxs-lookup"><span data-stu-id="9a470-117">Methods</span></span>  
  
|<span data-ttu-id="9a470-118">Имя метода</span><span class="sxs-lookup"><span data-stu-id="9a470-118">Method Name</span></span>|<span data-ttu-id="9a470-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9a470-119">Description</span></span>|<span data-ttu-id="9a470-120">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="9a470-120">C# Query Expression Syntax</span></span>|<span data-ttu-id="9a470-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9a470-121">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="9a470-122">Join две последовательности на основании функций селектора ключа и извлекает пары значений.</span><span class="sxs-lookup"><span data-stu-id="9a470-122">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="9a470-123">Join две последовательности на основании функций селектора ключа и группирует полученные при сопоставлении данные для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="9a470-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="9a470-124">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="9a470-124">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="9a470-125">В следующем примере предложение `join … in … on … equals …` используется для объединения двух последовательностей на основе конкретного значения.</span><span class="sxs-lookup"><span data-stu-id="9a470-125">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="9a470-126">В следующем примере используется предложение `join … in … on … equals … into …` для объединения двух последовательностей на основе конкретного значения, а полученные совпадения для каждого элемента группируются.</span><span class="sxs-lookup"><span data-stu-id="9a470-126">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="9a470-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9a470-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="9a470-128">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="9a470-128">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="9a470-129">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="9a470-129">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="9a470-130">Формулировка Join и запросов перекрестного произведения</span><span class="sxs-lookup"><span data-stu-id="9a470-130">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="9a470-131">предложение join</span><span class="sxs-lookup"><span data-stu-id="9a470-131">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="9a470-132">Join с помощью составных ключей</span><span class="sxs-lookup"><span data-stu-id="9a470-132">Join by using composite keys</span></span>](../../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="9a470-133">Объединение содержимого из файлов разных форматов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="9a470-133">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="9a470-134">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="9a470-134">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="9a470-135">Выполнение пользовательских операций соединения</span><span class="sxs-lookup"><span data-stu-id="9a470-135">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="9a470-136">Выполнение групповых соединений</span><span class="sxs-lookup"><span data-stu-id="9a470-136">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="9a470-137">Выполнение внутренних соединений</span><span class="sxs-lookup"><span data-stu-id="9a470-137">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="9a470-138">Выполнение левых внешних соединений</span><span class="sxs-lookup"><span data-stu-id="9a470-138">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="9a470-139">Заполнение коллекций объектов из нескольких источников (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="9a470-139">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
