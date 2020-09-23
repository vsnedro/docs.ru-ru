---
title: Практическое руководство. Сортировка результатов запроса с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: 94c2907f05aa9b5b2bc8659cef6f523187f1ef6b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071798"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="31159-102">Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31159-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="31159-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="31159-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="31159-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и сортирует результаты по нескольким полям с помощью `Order By` предложения.</span><span class="sxs-lookup"><span data-stu-id="31159-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="31159-105">Порядок сортировки для каждого поля может быть упорядочен по возрастанию или по убыванию.</span><span class="sxs-lookup"><span data-stu-id="31159-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="31159-106">Дополнительные сведения см. в разделе [предложение ORDER BY](../../../language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="31159-106">For more information, see [Order By Clause](../../../language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="31159-107">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="31159-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="31159-108">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="31159-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="31159-109">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="31159-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="31159-110">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="31159-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="31159-111">В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в **Server Explorer** / меню **вид** пункт Обозреватель сервера**Обозреватель базы данных** .</span><span class="sxs-lookup"><span data-stu-id="31159-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="31159-112">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных** а затем выберите команду **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="31159-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="31159-113">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="31159-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="31159-114">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="31159-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="31159-115">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="31159-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="31159-116">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="31159-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="31159-117">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="31159-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="31159-118">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="31159-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="31159-119">Задайте файлу имя `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="31159-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="31159-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="31159-120">Click **Add**.</span></span> <span data-ttu-id="31159-121">Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="31159-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="31159-122">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="31159-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="31159-123">В **Обозреватель сервера** / **Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="31159-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="31159-124">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="31159-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="31159-125">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="31159-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="31159-126">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="31159-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="31159-127">Щелкните таблицу Orders и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="31159-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="31159-128">Конструктор создает `Customer` `Order` для проекта новые объекты и.</span><span class="sxs-lookup"><span data-stu-id="31159-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="31159-129">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="31159-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="31159-130">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="31159-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="31159-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="31159-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="31159-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="31159-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="31159-133">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="31159-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="31159-134">Перетащите элемент управления из **области элементов**в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="31159-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="31159-135">Дважды щелкните Form1, чтобы добавить код в `Load` событие в форме.</span><span class="sxs-lookup"><span data-stu-id="31159-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="31159-136">При добавлении таблиц в реляционный конструктор объектов конструктор добавил в <xref:System.Data.Linq.DataContext> проект объект.</span><span class="sxs-lookup"><span data-stu-id="31159-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="31159-137">Этот объект содержит код, который необходим для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="31159-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="31159-138">Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="31159-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="31159-139">Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="31159-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="31159-140">В коде можно создать экземпляр класса <xref:System.Data.Linq.DataContext> и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="31159-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="31159-141">Добавьте следующий код в событие, `Load` чтобы запросить таблицы, предоставляемые как свойства контекста данных, и отсортировать результаты.</span><span class="sxs-lookup"><span data-stu-id="31159-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="31159-142">Запрос сортирует результаты по количеству заказов клиентов в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="31159-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="31159-143">Клиенты с одинаковым количеством заказов упорядочиваются по названию компании в возрастающем порядке (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="31159-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. <span data-ttu-id="31159-144">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="31159-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31159-145">См. также</span><span class="sxs-lookup"><span data-stu-id="31159-145">See also</span></span>

- [<span data-ttu-id="31159-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="31159-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="31159-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="31159-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="31159-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="31159-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="31159-149">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="31159-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
