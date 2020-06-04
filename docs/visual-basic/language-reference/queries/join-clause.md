---
title: Предложение Join
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359778"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="c54ea-102">Предложение Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54ea-102">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="c54ea-103">Объединяет две коллекции в одну.</span><span class="sxs-lookup"><span data-stu-id="c54ea-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="c54ea-104">Операция Join основана на совпадающих ключах и использует `Equals` оператор.</span><span class="sxs-lookup"><span data-stu-id="c54ea-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="c54ea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c54ea-105">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="c54ea-106">Компоненты</span><span class="sxs-lookup"><span data-stu-id="c54ea-106">Parts</span></span>

<span data-ttu-id="c54ea-107">`element` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c54ea-107">`element` Required.</span></span> <span data-ttu-id="c54ea-108">Управляющая переменная для объединяемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="c54ea-108">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="c54ea-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c54ea-109">Required.</span></span> <span data-ttu-id="c54ea-110">Коллекция для объединения с коллекцией, указанной в левой части `Join` оператора.</span><span class="sxs-lookup"><span data-stu-id="c54ea-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="c54ea-111">`Join`Предложение может быть вложенным в другое `Join` предложение или в `Group Join` предложении.</span><span class="sxs-lookup"><span data-stu-id="c54ea-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="c54ea-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c54ea-112">Optional.</span></span> <span data-ttu-id="c54ea-113">Одно или несколько дополнительных `Join` предложений для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="c54ea-113">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="c54ea-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c54ea-114">Optional.</span></span> <span data-ttu-id="c54ea-115">Одно или несколько дополнительных `Group Join` предложений для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="c54ea-115">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="c54ea-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="c54ea-116">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="c54ea-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c54ea-117">Required.</span></span> <span data-ttu-id="c54ea-118">Определяет ключи для соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="c54ea-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="c54ea-119">`Equals`Для сравнения ключей из объединяемых коллекций необходимо использовать оператор.</span><span class="sxs-lookup"><span data-stu-id="c54ea-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="c54ea-120">Условия объединения можно комбинировать с помощью `And` оператора для обнаружения нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="c54ea-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="c54ea-121">`key1`должен быть из коллекции в левой части `Join` оператора.</span><span class="sxs-lookup"><span data-stu-id="c54ea-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="c54ea-122">`key2`должен находиться в коллекции с правой стороны `Join` оператора.</span><span class="sxs-lookup"><span data-stu-id="c54ea-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="c54ea-123">Ключи, используемые в условии объединения, могут быть выражениями, включающими более одного элемента из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c54ea-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="c54ea-124">Однако каждое ключевое выражение может содержать только элементы из соответствующей коллекции.</span><span class="sxs-lookup"><span data-stu-id="c54ea-124">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="c54ea-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c54ea-125">Remarks</span></span>

<span data-ttu-id="c54ea-126">`Join`Предложение объединяет две коллекции на основе совпадающих значений ключей из объединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="c54ea-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="c54ea-127">Результирующая коллекция может содержать любое сочетание значений из коллекции, указанной в левой части `Join` оператора, и коллекции, указанной в `Join` предложении.</span><span class="sxs-lookup"><span data-stu-id="c54ea-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="c54ea-128">Запрос возвратит только результаты, для которых выполняется условие, заданное `Equals` оператором.</span><span class="sxs-lookup"><span data-stu-id="c54ea-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="c54ea-129">Это эквивалентно `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="c54ea-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="c54ea-130">`Join`Для объединения двух или более коллекций в одну коллекцию можно использовать несколько предложений в запросе.</span><span class="sxs-lookup"><span data-stu-id="c54ea-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="c54ea-131">Можно выполнить неявное соединение для объединения коллекций без `Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="c54ea-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="c54ea-132">Для этого включите `In` в предложение несколько предложений `From` и укажите `Where` предложение, определяющее ключи, которые необходимо использовать для объединения.</span><span class="sxs-lookup"><span data-stu-id="c54ea-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="c54ea-133">Предложение можно использовать `Group Join` для объединения коллекций в одну иерархическую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="c54ea-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="c54ea-134">Это похоже на `LEFT OUTER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="c54ea-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="c54ea-135">Пример</span><span class="sxs-lookup"><span data-stu-id="c54ea-135">Example</span></span>

<span data-ttu-id="c54ea-136">В следующем примере кода выполняется неявное соединение для объединения списка клиентов с их заказами.</span><span class="sxs-lookup"><span data-stu-id="c54ea-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="c54ea-137">Пример</span><span class="sxs-lookup"><span data-stu-id="c54ea-137">Example</span></span>

<span data-ttu-id="c54ea-138">В следующем примере кода две коллекции объединяются с помощью `Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="c54ea-138">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="c54ea-139">В этом примере выводятся выходные данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="c54ea-139">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="c54ea-140">Пример</span><span class="sxs-lookup"><span data-stu-id="c54ea-140">Example</span></span>

<span data-ttu-id="c54ea-141">В следующем примере кода две коллекции соединяются с помощью `Join` предложения с двумя ключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="c54ea-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="c54ea-142">В примере будет выведен результат, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="c54ea-142">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="c54ea-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c54ea-143">See also</span></span>

- <span data-ttu-id="c54ea-144">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54ea-144">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="c54ea-145">Запросы</span><span class="sxs-lookup"><span data-stu-id="c54ea-145">Queries</span></span>](index.md)
- [<span data-ttu-id="c54ea-146">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="c54ea-146">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="c54ea-147">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="c54ea-147">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="c54ea-148">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="c54ea-148">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="c54ea-149">Предложение WHERE</span><span class="sxs-lookup"><span data-stu-id="c54ea-149">Where Clause</span></span>](where-clause.md)
