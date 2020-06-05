---
title: Практическое руководство. Выполнение запросов к базе данных с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: ad4744e1734fd968f610ec02b60814eadd3ebe9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404969"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="339e2-102">Практическое руководство. Выполнение запросов к базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="339e2-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="339e2-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="339e2-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="339e2-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="339e2-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="339e2-105">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="339e2-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="339e2-106">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="339e2-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="339e2-107">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="339e2-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="339e2-108">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="339e2-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="339e2-109">В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в **Server Explorer** / меню **вид** пункт Обозреватель сервера**Обозреватель базы данных** .</span><span class="sxs-lookup"><span data-stu-id="339e2-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="339e2-110">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных** а затем выберите команду **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="339e2-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="339e2-111">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="339e2-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="339e2-112">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="339e2-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="339e2-113">В Visual Studio в меню **файл** наведите указатель мыши на пункт **создать** и выберите **проект**.</span><span class="sxs-lookup"><span data-stu-id="339e2-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="339e2-114">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="339e2-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="339e2-115">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="339e2-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="339e2-116">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="339e2-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="339e2-117">Задайте файлу имя `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="339e2-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="339e2-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="339e2-118">Click **Add**.</span></span> <span data-ttu-id="339e2-119">Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="339e2-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="339e2-120">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="339e2-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="339e2-121">В **Обозреватель сервера** / **Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="339e2-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="339e2-122">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="339e2-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="339e2-123">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="339e2-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="339e2-124">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="339e2-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="339e2-125">Щелкните таблицу Orders и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="339e2-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="339e2-126">Конструктор создает `Customer` `Order` для проекта новые объекты и.</span><span class="sxs-lookup"><span data-stu-id="339e2-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="339e2-127">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="339e2-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="339e2-128">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="339e2-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="339e2-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="339e2-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="339e2-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="339e2-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="339e2-131">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="339e2-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="339e2-132">Перетащите элемент управления из **области элементов**в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="339e2-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="339e2-133">Дважды щелкните Form1, чтобы добавить код в `Load` событие в форме.</span><span class="sxs-lookup"><span data-stu-id="339e2-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="339e2-134">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="339e2-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="339e2-135">Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="339e2-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="339e2-136">Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="339e2-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="339e2-137">Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="339e2-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="339e2-138">В коде можно создать экземпляр класса <xref:System.Data.Linq.DataContext> и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="339e2-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="339e2-139">Добавьте следующий код в `Load` событие для запроса таблиц, предоставляемых в качестве свойств контекста данных.</span><span class="sxs-lookup"><span data-stu-id="339e2-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="339e2-140">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="339e2-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="339e2-141">Ниже приведены некоторые дополнительные запросы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="339e2-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="339e2-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="339e2-142">See also</span></span>

- [<span data-ttu-id="339e2-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="339e2-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="339e2-144">Запросы</span><span class="sxs-lookup"><span data-stu-id="339e2-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="339e2-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="339e2-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="339e2-146">Методы DataContext (реляционный конструктор R)</span><span class="sxs-lookup"><span data-stu-id="339e2-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
