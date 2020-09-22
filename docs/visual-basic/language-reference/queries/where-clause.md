---
title: Предложение Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 3a43554fb25592bf413525a2df109010e4868492
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869637"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="267e0-102">Предложение Where (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="267e0-102">Where Clause (Visual Basic)</span></span>

<span data-ttu-id="267e0-103">Задает условие фильтрации для запроса.</span><span class="sxs-lookup"><span data-stu-id="267e0-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="267e0-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="267e0-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="267e0-105">Parts</span></span>  

 `condition`  
 <span data-ttu-id="267e0-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="267e0-106">Required.</span></span> <span data-ttu-id="267e0-107">Выражение, определяющее, включаются ли значения для текущего элемента в коллекции в выходную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="267e0-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="267e0-108">Выражение должно иметь `Boolean` значение или эквивалент `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="267e0-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="267e0-109">Если условие принимает значение `True` , элемент включается в результат запроса; в противном случае элемент исключается из результата запроса.</span><span class="sxs-lookup"><span data-stu-id="267e0-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="267e0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="267e0-110">Remarks</span></span>  

 <span data-ttu-id="267e0-111">`Where`Предложение позволяет фильтровать данные запроса, выбирая только те элементы, которые соответствуют определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="267e0-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="267e0-112">Элементы, значения которых приводят к `Where` вычислению предложения `True` , включаются в результат запроса; другие элементы исключаются.</span><span class="sxs-lookup"><span data-stu-id="267e0-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="267e0-113">Выражение, используемое в `Where` предложении, должно возвращать значение `Boolean` или эквивалент типа `Boolean` , например целое число, которое вычисляется, `False` если его значение равно нулю.</span><span class="sxs-lookup"><span data-stu-id="267e0-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="267e0-114">В предложении можно объединить несколько выражений, `Where` используя логические операторы, такие как `And` ,, `Or` ,, `AndAlso` `OrElse` `Is` и `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="267e0-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="267e0-115">По умолчанию выражения запроса не оцениваются до тех пор, пока они не будут доступны, например, когда они привязаны к данным или просматриваются в `For` цикле.</span><span class="sxs-lookup"><span data-stu-id="267e0-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="267e0-116">В результате это `Where` предложение не вычисляется до тех пор, пока не будет осуществлен доступ к запросу.</span><span class="sxs-lookup"><span data-stu-id="267e0-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="267e0-117">При наличии внешних значений для запроса, которые используются в `Where` предложении, убедитесь, что в `Where` предложении во время выполнения запроса используется соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="267e0-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="267e0-118">Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="267e0-118">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="267e0-119">Можно вызывать функции внутри предложения, `Where` чтобы выполнить вычисление или операцию над значением из текущего элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="267e0-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="267e0-120">Вызов функции в `Where` предложении может привести к немедленному выполнению запроса, если он определен, а не при обращении к нему.</span><span class="sxs-lookup"><span data-stu-id="267e0-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="267e0-121">Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="267e0-121">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="267e0-122">Пример</span><span class="sxs-lookup"><span data-stu-id="267e0-122">Example</span></span>  

 <span data-ttu-id="267e0-123">Следующее выражение запроса использует `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции.</span><span class="sxs-lookup"><span data-stu-id="267e0-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="267e0-124">`Where`Предложение использует переменную диапазона для ограничения выходных данных для клиентов из указанной области.</span><span class="sxs-lookup"><span data-stu-id="267e0-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="267e0-125">`For Each`Цикл отображает название компании для каждого клиента в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="267e0-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="267e0-126">Пример</span><span class="sxs-lookup"><span data-stu-id="267e0-126">Example</span></span>  

 <span data-ttu-id="267e0-127">В следующем примере используются `And` и `Or` логические операторы в `Where` предложении.</span><span class="sxs-lookup"><span data-stu-id="267e0-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="267e0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="267e0-128">See also</span></span>

- <span data-ttu-id="267e0-129">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="267e0-129">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="267e0-130">Запросы</span><span class="sxs-lookup"><span data-stu-id="267e0-130">Queries</span></span>](index.md)
- [<span data-ttu-id="267e0-131">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="267e0-131">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="267e0-132">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="267e0-132">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="267e0-133">Оператор For Each…Next</span><span class="sxs-lookup"><span data-stu-id="267e0-133">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
