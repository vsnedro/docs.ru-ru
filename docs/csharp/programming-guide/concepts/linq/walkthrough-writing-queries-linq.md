---
title: Пошаговое руководство. Написание запросов на C# (LINQ)
description: В этом руководстве описываются возможности C#, используемые в выражениях запросов LINQ. В этой статье в качестве среды разработки используется Visual Studio.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: bdf91f6f52a68309cfcd276b222083c8cb67a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176244"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="0bb74-104">Пошаговое руководство. Написание запросов на C# (LINQ)</span><span class="sxs-lookup"><span data-stu-id="0bb74-104">Walkthrough: Writing Queries in C# (LINQ)</span></span>

<span data-ttu-id="0bb74-105">В этом пошаговом руководстве описываются возможности C#, предназначенные для написания выражений запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="0bb74-105">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="0bb74-106">Создание проекта C#</span><span class="sxs-lookup"><span data-stu-id="0bb74-106">Create a C# Project</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0bb74-107">Приведенные ниже инструкции относятся к Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bb74-107">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="0bb74-108">Если вы пользуетесь другой средой разработки, создайте консольный проект со ссылкой на библиотеку System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0bb74-108">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="0bb74-109">Создание проекта в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0bb74-109">To create a project in Visual Studio</span></span>  
  
1. <span data-ttu-id="0bb74-110">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bb74-110">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="0bb74-111">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="0bb74-111">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="0bb74-112">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="0bb74-112">The **New Project** dialog box opens.</span></span>  
  
3. <span data-ttu-id="0bb74-113">Последовательно разверните узлы **Установленные**, **Шаблоны** и **Visual C#** , а затем выберите **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="0bb74-113">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4. <span data-ttu-id="0bb74-114">В текстовое поле **Имя** введите другое имя или примите имя по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0bb74-114">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="0bb74-115">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="0bb74-115">The new project appears in **Solution Explorer**.</span></span>  
  
5. <span data-ttu-id="0bb74-116">Обратите внимание, что проект содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0bb74-116">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="0bb74-117">Создание источника данных в памяти</span><span class="sxs-lookup"><span data-stu-id="0bb74-117">Create an in-Memory Data Source</span></span>  

 <span data-ttu-id="0bb74-118">Источником данных для запросов является простой список объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-118">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="0bb74-119">Каждая запись `Student` включает имя, фамилию и массив целых чисел, соответствующих их баллам за проведенные в классе тесты.</span><span class="sxs-lookup"><span data-stu-id="0bb74-119">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="0bb74-120">Скопируйте этот код в проект.</span><span class="sxs-lookup"><span data-stu-id="0bb74-120">Copy this code into your project.</span></span> <span data-ttu-id="0bb74-121">Обратите внимание на следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="0bb74-121">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="0bb74-122">Класс `Student` состоит из автоматически внедренных свойств.</span><span class="sxs-lookup"><span data-stu-id="0bb74-122">The `Student` class consists of auto-implemented properties.</span></span>  
  
- <span data-ttu-id="0bb74-123">Каждый учащийся в списке инициализируется соответствующим инициализатором объекта.</span><span class="sxs-lookup"><span data-stu-id="0bb74-123">Each student in the list is initialized with an object initializer.</span></span>  
  
- <span data-ttu-id="0bb74-124">Сам список инициализируется инициализатором коллекции.</span><span class="sxs-lookup"><span data-stu-id="0bb74-124">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="0bb74-125">Вся эта структура данных инициализируется и создается без явных вызовов какого-либо конструктора или прямого доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="0bb74-125">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="0bb74-126">Дополнительные сведения об этих новых возможностях см. в разделах [Автоматически внедренные свойства](../../classes-and-structs/auto-implemented-properties.md) и [Инициализаторы объектов и коллекций](../../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="0bb74-126">For more information about these new features, see [Auto-Implemented Properties](../../classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="0bb74-127">Добавление источника данных</span><span class="sxs-lookup"><span data-stu-id="0bb74-127">To add the data source</span></span>  
  
- <span data-ttu-id="0bb74-128">Добавьте класс `Student` и инициализированный список учащихся в класс `Program` в проекте.</span><span class="sxs-lookup"><span data-stu-id="0bb74-128">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="0bb74-129">Добавление нового учащегося в список учащихся</span><span class="sxs-lookup"><span data-stu-id="0bb74-129">To add a new Student to the Students list</span></span>  
  
1. <span data-ttu-id="0bb74-130">Добавьте новый объект `Student` в список `Students` и введите любое имя и результаты тестирования.</span><span class="sxs-lookup"><span data-stu-id="0bb74-130">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="0bb74-131">Чтобы лучше изучить синтаксис инициализатора объекта, постарайтесь заполнить все данные нового учащегося.</span><span class="sxs-lookup"><span data-stu-id="0bb74-131">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="0bb74-132">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="0bb74-132">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="0bb74-133">Создание простого запроса</span><span class="sxs-lookup"><span data-stu-id="0bb74-133">To create a simple query</span></span>  
  
- <span data-ttu-id="0bb74-134">В методе `Main` приложения создайте простой запрос, при выполнении которого будет возвращаться список учащихся, набравших в результате тестирования больше 90 баллов.</span><span class="sxs-lookup"><span data-stu-id="0bb74-134">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="0bb74-135">Поскольку выбран весь объект `Student`, запрос имеет тип `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-135">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="0bb74-136">Несмотря на то, что код можно также набрать напрямую, используя ключевое слово [var](../../../language-reference/keywords/var.md), для демонстрации результатов применяется неявная типизация.</span><span class="sxs-lookup"><span data-stu-id="0bb74-136">Although the code could also use implicit typing by using the [var](../../../language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="0bb74-137">(Дополнительные сведения о `var` см. в разделе [Неявно типизированные локальные переменные](../../classes-and-structs/implicitly-typed-local-variables.md).)</span><span class="sxs-lookup"><span data-stu-id="0bb74-137">(For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="0bb74-138">Кроме того переменная диапазона в запросе, `student`, служит ссылкой на каждый объект `Student` в источнике и предоставляет доступ к каждому объекту.</span><span class="sxs-lookup"><span data-stu-id="0bb74-138">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="0bb74-139">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="0bb74-139">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="0bb74-140">Порядок выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="0bb74-140">To execute the query</span></span>  
  
1. <span data-ttu-id="0bb74-141">Теперь напишите цикл `foreach`, вызывающий выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="0bb74-141">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="0bb74-142">Обратите внимание на следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="0bb74-142">Note the following about the code:</span></span>  
  
    - <span data-ttu-id="0bb74-143">Доступ к каждому элементу в возвращаемой последовательности осуществляется с помощью переменной итерации в цикле `foreach`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-143">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    - <span data-ttu-id="0bb74-144">Эта переменная имеет тип `Student`, а переменная запроса — совместимый тип `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-144">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2. <span data-ttu-id="0bb74-145">Добавив код, соберите и запустите приложение, чтобы отобразить результаты в окне **Консоль**.</span><span class="sxs-lookup"><span data-stu-id="0bb74-145">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="0bb74-146">Добавление другого условия фильтра</span><span class="sxs-lookup"><span data-stu-id="0bb74-146">To add another filter condition</span></span>  
  
1. <span data-ttu-id="0bb74-147">Чтобы сделать запрос более точным, можно объединить несколько логических условий в предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-147">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="0bb74-148">Следующий код добавляет условие, согласно которому запрос возвращает учащихся, которые по первому тесту набрали больше 90 баллов, а по последнему — меньше 80 баллов.</span><span class="sxs-lookup"><span data-stu-id="0bb74-148">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="0bb74-149">Предложение `where` должно быть аналогично приведенному ниже коду.</span><span class="sxs-lookup"><span data-stu-id="0bb74-149">The `where` clause should resemble the following code.</span></span>  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="0bb74-150">Дополнительные сведения см. в разделе [Предложение where](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0bb74-150">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="0bb74-151">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="0bb74-151">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="0bb74-152">Упорядочение результатов</span><span class="sxs-lookup"><span data-stu-id="0bb74-152">To order the results</span></span>  
  
1. <span data-ttu-id="0bb74-153">С результатами проще работать, если они упорядочены.</span><span class="sxs-lookup"><span data-stu-id="0bb74-153">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="0bb74-154">Возвращаемую последовательность можно упорядочить по любому доступному полю в исходных элементах.</span><span class="sxs-lookup"><span data-stu-id="0bb74-154">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="0bb74-155">Например, следующее предложение `orderby` упорядочивает результаты в алфавитном порядке от А до Z, используя фамилии учащихся.</span><span class="sxs-lookup"><span data-stu-id="0bb74-155">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="0bb74-156">Добавьте к запросу следующее предложение `orderby`, указав его после оператора `where` и перед оператором `select`:</span><span class="sxs-lookup"><span data-stu-id="0bb74-156">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. <span data-ttu-id="0bb74-157">Теперь измените предложение `orderby` таким образом, чтобы результаты были упорядочены по баллам за первый тест в обратном порядке, от наибольшего к наименьшему.</span><span class="sxs-lookup"><span data-stu-id="0bb74-157">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. <span data-ttu-id="0bb74-158">Измените строку формата `WriteLine` таким образом, чтобы отобразить баллы:</span><span class="sxs-lookup"><span data-stu-id="0bb74-158">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="0bb74-159">Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0bb74-159">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="0bb74-160">Группировка результатов</span><span class="sxs-lookup"><span data-stu-id="0bb74-160">To group the results</span></span>  
  
1. <span data-ttu-id="0bb74-161">Группировка представляет собой полезную возможность в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="0bb74-161">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="0bb74-162">Запрос с предложением group создает последовательность групп, в которой каждая группа содержит `Key`, и последовательность, состоящую из всех членов этой группы.</span><span class="sxs-lookup"><span data-stu-id="0bb74-162">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="0bb74-163">Представленный ниже запрос группирует учащихся, используя в качестве ключа первую букву фамилии.</span><span class="sxs-lookup"><span data-stu-id="0bb74-163">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. <span data-ttu-id="0bb74-164">Обратите внимание на то, что тип запроса изменился.</span><span class="sxs-lookup"><span data-stu-id="0bb74-164">Note that the type of the query has now changed.</span></span> <span data-ttu-id="0bb74-165">Теперь он создает последовательность групп с типом `char` в качестве ключа и последовательность объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-165">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="0bb74-166">Поскольку тип запроса изменился, следующий код изменяет также цикл выполнения `foreach`:</span><span class="sxs-lookup"><span data-stu-id="0bb74-166">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. <span data-ttu-id="0bb74-167">Запустите приложение и просмотрите результаты в окне **Консоль**.</span><span class="sxs-lookup"><span data-stu-id="0bb74-167">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="0bb74-168">Дополнительные сведения см. в разделе [Предложение group](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0bb74-168">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="0bb74-169">Преобразование переменных в явно типизированные</span><span class="sxs-lookup"><span data-stu-id="0bb74-169">To make the variables implicitly typed</span></span>  
  
1. <span data-ttu-id="0bb74-170">Набирать код `IEnumerables` в `IGroupings` напрямую — далеко не самое увлекательное занятие.</span><span class="sxs-lookup"><span data-stu-id="0bb74-170">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="0bb74-171">Написать тот же запрос и цикл `foreach` можно быстрее и проще, воспользовавшись переменной `var`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-171">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="0bb74-172">Ключевое слово `var` не приводит к изменению типов объектов, оно просто сообщает компилятору о том, что он должен вывести типы логически.</span><span class="sxs-lookup"><span data-stu-id="0bb74-172">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="0bb74-173">Измените тип `studentQuery` и переменную итерации `group` на `var` и выполните запрос заново.</span><span class="sxs-lookup"><span data-stu-id="0bb74-173">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="0bb74-174">Обратите внимание на то, что во внутреннем цикле `foreach` переменная итерации по-прежнему типизируется как `Student`, а запрос работает так же, как раньше.</span><span class="sxs-lookup"><span data-stu-id="0bb74-174">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="0bb74-175">Измените переменную итерации `s` на `var` и выполните запрос заново.</span><span class="sxs-lookup"><span data-stu-id="0bb74-175">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="0bb74-176">Результаты будут точно такими же.</span><span class="sxs-lookup"><span data-stu-id="0bb74-176">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     <span data-ttu-id="0bb74-177">Дополнительные сведения о переменной [var](../../../language-reference/keywords/var.md) см. в разделе [Неявно типизированные локальные переменные](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="0bb74-177">For more information about [var](../../../language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="0bb74-178">Упорядочение групп по значению ключа</span><span class="sxs-lookup"><span data-stu-id="0bb74-178">To order the groups by their key value</span></span>  
  
1. <span data-ttu-id="0bb74-179">Выполняя предыдущий запрос, вы могли заметить, что группы отображаются не в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="0bb74-179">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="0bb74-180">Для того чтобы это изменить, необходимо указать предложение `orderby` после предложения `group`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-180">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="0bb74-181">Но, чтобы использовать предложение `orderby`, нужен идентификатор, служащий в качестве ссылки на группы, создаваемые предложением `group`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-181">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="0bb74-182">Укажите идентификатор с помощью ключевого слова `into`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="0bb74-182">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     <span data-ttu-id="0bb74-183">После выполнения этого запроса группы будут отсортированы в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="0bb74-183">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="0bb74-184">Введение идентификаторов с помощью предложения let</span><span class="sxs-lookup"><span data-stu-id="0bb74-184">To introduce an identifier by using let</span></span>  
  
1. <span data-ttu-id="0bb74-185">Ключевое слово `let` позволяет ввести идентификатор для любого результата в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="0bb74-185">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="0bb74-186">Этот идентификатор может применяться для удобства, как в следующем примере, или повышать производительность, сохраняя результаты выражения, чтобы не вычислять их повторно.</span><span class="sxs-lookup"><span data-stu-id="0bb74-186">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     <span data-ttu-id="0bb74-187">Дополнительные сведения см. в разделе [Предложение let](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0bb74-187">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="0bb74-188">Использование синтаксиса метода в выражении запроса</span><span class="sxs-lookup"><span data-stu-id="0bb74-188">To use method syntax in a query expression</span></span>  
  
1. <span data-ttu-id="0bb74-189">Как описано в разделе [Синтаксис запросов и синтаксис методов в LINQ](./query-syntax-and-method-syntax-in-linq.md), некоторые операции запросов можно выразить, только используя синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="0bb74-189">As described in [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="0bb74-190">Представленный ниже код вычисляет общий балл для каждого объекта `Student` в исходной последовательности, а затем применяет метод `Average()` к результатам запроса, чтобы рассчитать средний балл класса.</span><span class="sxs-lookup"><span data-stu-id="0bb74-190">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span>
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="0bb74-191">Преобразование или проецирование в предложение select</span><span class="sxs-lookup"><span data-stu-id="0bb74-191">To transform or project in the select clause</span></span>  
  
1. <span data-ttu-id="0bb74-192">Запрос очень часто выдает последовательность, элементы которой отличаются от элементов в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="0bb74-192">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="0bb74-193">Удалите или закомментируйте предыдущий запрос и цикл выполнения и замените его на представленный ниже код.</span><span class="sxs-lookup"><span data-stu-id="0bb74-193">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="0bb74-194">Обратите внимание на то, что запрос возвращает последовательность строк (не `Students`), и этот факт отражается в цикле `foreach`.</span><span class="sxs-lookup"><span data-stu-id="0bb74-194">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. <span data-ttu-id="0bb74-195">Код, представленный выше в этом пошаговом руководстве, показывает, что среднее количество баллов по классу составляет около 334.</span><span class="sxs-lookup"><span data-stu-id="0bb74-195">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="0bb74-196">Для создания последовательности `Students`, сумма баллов в которой будет выше, чем средний показатель по классу, с указанием `Student ID` можно вставить в оператор `select` анонимный тип:</span><span class="sxs-lookup"><span data-stu-id="0bb74-196">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a><span data-ttu-id="0bb74-197">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="0bb74-197">Next Steps</span></span>  

 <span data-ttu-id="0bb74-198">Ознакомившись с основными аспектами работы с запросами в C#, вы будете готовы прочитать документацию и примеры по интересующему вас типу поставщика LINQ:</span><span class="sxs-lookup"><span data-stu-id="0bb74-198">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="0bb74-199">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0bb74-199">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="0bb74-200">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0bb74-200">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="0bb74-201">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="0bb74-201">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)  
  
 [<span data-ttu-id="0bb74-202">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="0bb74-202">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="0bb74-203">См. также</span><span class="sxs-lookup"><span data-stu-id="0bb74-203">See also</span></span>

- [<span data-ttu-id="0bb74-204">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="0bb74-204">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="0bb74-205">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="0bb74-205">LINQ Query Expressions</span></span>](../../../linq/index.md)
