---
title: Практическое руководство. Объединение данных с помощью LINQ с использованием соединений
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: ebda8d3b7fa2e712c337ed2c1fadc580bed7fe61
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075074"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="24295-102">Практическое руководство. Объединение данных с помощью LINQ с использованием соединений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24295-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>

<span data-ttu-id="24295-103">Visual Basic предоставляет `Join` предложения запросов и, позволяющие `Group Join` объединять содержимое нескольких коллекций на основе общих значений между коллекциями.</span><span class="sxs-lookup"><span data-stu-id="24295-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="24295-104">Эти значения называются значениями *ключа* .</span><span class="sxs-lookup"><span data-stu-id="24295-104">These values are known as *key* values.</span></span> <span data-ttu-id="24295-105">Разработчики, знакомые с концепциями реляционных баз данных, распознают `Join` предложение как внутреннее соединение и `Group Join` предложение как, фактически, левое внешнее соединение.</span><span class="sxs-lookup"><span data-stu-id="24295-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="24295-106">Примеры в этом разделе демонстрируют несколько способов объединения данных с помощью `Join` `Group Join` предложений запросов и.</span><span class="sxs-lookup"><span data-stu-id="24295-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="24295-107">Создание проекта и добавление демонстрационных данных</span><span class="sxs-lookup"><span data-stu-id="24295-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="24295-108">Создание проекта, содержащего образцы данных и типы</span><span class="sxs-lookup"><span data-stu-id="24295-108">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="24295-109">Чтобы выполнить примеры в этом разделе, откройте Visual Studio и добавьте новый проект Visual Basic консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="24295-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="24295-110">Дважды щелкните файл Module1. vb, созданный Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="24295-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="24295-111">В примерах в этом разделе используются `Person` `Pet` типы и и данные из следующего примера кода.</span><span class="sxs-lookup"><span data-stu-id="24295-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="24295-112">Скопируйте этот код в модуль по умолчанию `Module1` , созданный Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="24295-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="24295-113">Выполнение внутреннего объединения с помощью предложения Join</span><span class="sxs-lookup"><span data-stu-id="24295-113">Perform an Inner Join by Using the Join Clause</span></span>  

 <span data-ttu-id="24295-114">ВНУТРЕННЕЕ соединение объединяет данные из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="24295-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="24295-115">Включаются элементы, для которых совпадают указанные значения ключа.</span><span class="sxs-lookup"><span data-stu-id="24295-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="24295-116">Все элементы из любой коллекции, не имеющие соответствующего элемента в другой коллекции, исключаются.</span><span class="sxs-lookup"><span data-stu-id="24295-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="24295-117">В Visual Basic LINQ предоставляет два варианта выполнения внутреннего объединения: неявное соединение и явное соединение.</span><span class="sxs-lookup"><span data-stu-id="24295-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="24295-118">Неявное соединение задает коллекции для объединения в `From` предложении и определяет соответствующие ключевые поля в `Where` предложении.</span><span class="sxs-lookup"><span data-stu-id="24295-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="24295-119">Visual Basic неявно соединяет две коллекции на основе указанных ключевых полей.</span><span class="sxs-lookup"><span data-stu-id="24295-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="24295-120">Можно указать явное соединение с помощью предложения, `Join` Если необходимо определить, какие ключевые поля использовать в соединении.</span><span class="sxs-lookup"><span data-stu-id="24295-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="24295-121">В этом случае `Where` предложение по-прежнему можно использовать для фильтрации результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="24295-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="24295-122">Выполнение внутреннего объединения с помощью предложения Join</span><span class="sxs-lookup"><span data-stu-id="24295-122">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="24295-123">Добавьте следующий код в `Module1` модуль проекта, чтобы увидеть примеры как неявного, так и неявного внутреннего объединения.</span><span class="sxs-lookup"><span data-stu-id="24295-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="24295-124">Выполнение левого внешнего объединения с помощью предложения Group Join</span><span class="sxs-lookup"><span data-stu-id="24295-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  

 <span data-ttu-id="24295-125">ЛЕВОЕ ВНЕШНее соединение включает все элементы из левой коллекции объединения и только совпадающие значения из правой коллекции объединения.</span><span class="sxs-lookup"><span data-stu-id="24295-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="24295-126">Все элементы из правой коллекции объединения, не имеющие соответствующего элемента в коллекции слева, исключаются из результата запроса.</span><span class="sxs-lookup"><span data-stu-id="24295-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="24295-127">`Group Join`Предложение, по сути, ВЫПОЛНЯЕТ левое внешнее соединение.</span><span class="sxs-lookup"><span data-stu-id="24295-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="24295-128">Разница между тем, что обычно известно как левое ВНЕШНее соединение, и то `Group Join` , что возвращает предложение, заключается в том, что `Group Join` предложение группирует результаты из правой коллекции объединения для каждого элемента в левой коллекции.</span><span class="sxs-lookup"><span data-stu-id="24295-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="24295-129">В реляционной базе данных левое ВНЕШНее соединение возвращает несгруппированный результат, в котором каждый элемент в результатах запроса содержит совпадающие элементы из обеих коллекций в соединении.</span><span class="sxs-lookup"><span data-stu-id="24295-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="24295-130">В этом случае элементы из левой коллекции объединения повторяются для каждого совпадающего элемента из правой коллекции.</span><span class="sxs-lookup"><span data-stu-id="24295-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="24295-131">Вы увидите, как это выглядит при выполнении следующей процедуры.</span><span class="sxs-lookup"><span data-stu-id="24295-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="24295-132">Результаты запроса можно получить в `Group Join` виде несгруппированного результата, расширив запрос, чтобы вернуть элемент для каждого сгруппированного результата запроса.</span><span class="sxs-lookup"><span data-stu-id="24295-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="24295-133">Для этого необходимо убедиться, что выполняется запрос к `DefaultIfEmpty` методу сгруппированной коллекции.</span><span class="sxs-lookup"><span data-stu-id="24295-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="24295-134">Это гарантирует, что элементы из левой коллекции объединения по-прежнему будут включены в результат запроса, даже если они не имеют соответствующих результатов из коллекции справа.</span><span class="sxs-lookup"><span data-stu-id="24295-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="24295-135">Можно добавить код в запрос, чтобы предоставить значение результата по умолчанию при отсутствии совпадающего значения из правой коллекции объединения.</span><span class="sxs-lookup"><span data-stu-id="24295-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="24295-136">Выполнение левого внешнего объединения с помощью предложения Group Join</span><span class="sxs-lookup"><span data-stu-id="24295-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="24295-137">Добавьте следующий код в `Module1` модуль проекта, чтобы увидеть примеры сгруппированного левого внешнего объединения и несгруппированного левого внешнего объединения.</span><span class="sxs-lookup"><span data-stu-id="24295-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="24295-138">Выполнение объединения с помощью составного ключа</span><span class="sxs-lookup"><span data-stu-id="24295-138">Perform a Join by Using a Composite Key</span></span>  

 <span data-ttu-id="24295-139">`And`Ключевое слово в `Join` предложении или можно использовать `Group Join` для обнаружения нескольких ключевых полей, используемых при сопоставлении значений из объединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="24295-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="24295-140">`And`Ключевое слово указывает, что все указанные ключевые поля должны совпадать для соединяемых элементов.</span><span class="sxs-lookup"><span data-stu-id="24295-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="24295-141">Выполнение объединения с помощью составного ключа</span><span class="sxs-lookup"><span data-stu-id="24295-141">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="24295-142">Добавьте следующий код в `Module1` модуль проекта, чтобы увидеть примеры соединений, использующих составной ключ.</span><span class="sxs-lookup"><span data-stu-id="24295-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="24295-143">Запуск кода</span><span class="sxs-lookup"><span data-stu-id="24295-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="24295-144">Добавление кода для выполнения примеров</span><span class="sxs-lookup"><span data-stu-id="24295-144">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="24295-145">Замените `Sub Main` в `Module1` модуле в проекте на следующий код, чтобы выполнить примеры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="24295-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="24295-146">Нажмите клавишу F5, чтобы выполнить примеры.</span><span class="sxs-lookup"><span data-stu-id="24295-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24295-147">См. также</span><span class="sxs-lookup"><span data-stu-id="24295-147">See also</span></span>

- [<span data-ttu-id="24295-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="24295-148">LINQ</span></span>](index.md)
- <span data-ttu-id="24295-149">[Introduction to LINQ in Visual Basic](introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24295-149">[Introduction to LINQ in Visual Basic](introduction-to-linq.md)</span></span>
- [<span data-ttu-id="24295-150">Предложение Join</span><span class="sxs-lookup"><span data-stu-id="24295-150">Join Clause</span></span>](../../../language-reference/queries/join-clause.md)
- [<span data-ttu-id="24295-151">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="24295-151">Group Join Clause</span></span>](../../../language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="24295-152">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="24295-152">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="24295-153">Предложение WHERE</span><span class="sxs-lookup"><span data-stu-id="24295-153">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="24295-154">Запросы</span><span class="sxs-lookup"><span data-stu-id="24295-154">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="24295-155">Преобразования данных с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="24295-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
