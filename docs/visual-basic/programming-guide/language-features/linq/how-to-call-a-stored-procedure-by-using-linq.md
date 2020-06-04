---
title: Практическое руководство. Вызов хранимой процедуры с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: b451642a16f36c4f7fd19c853fdfd2282f5bede5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405034"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="3670b-102">Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3670b-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="3670b-103">LINQ позволяет легко получить доступ к информации базы данных, включая объекты базы данных, такие как хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="3670b-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="3670b-104">В следующем примере показано, как создать приложение, вызывающее хранимую процедуру в SQL Server базе данных.</span><span class="sxs-lookup"><span data-stu-id="3670b-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="3670b-105">В этом примере показано, как вызвать две различные хранимые процедуры в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3670b-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="3670b-106">Каждая процедура возвращает результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="3670b-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="3670b-107">Одна процедура принимает входные параметры, а другая процедура не принимает параметры.</span><span class="sxs-lookup"><span data-stu-id="3670b-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="3670b-108">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="3670b-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="3670b-109">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3670b-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="3670b-110">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3670b-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="3670b-111">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="3670b-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="3670b-112">В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в **Server Explorer** / меню **вид** пункт Обозреватель сервера**Обозреватель базы данных** .</span><span class="sxs-lookup"><span data-stu-id="3670b-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="3670b-113">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных** а затем выберите команду **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="3670b-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="3670b-114">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="3670b-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="3670b-115">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3670b-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="3670b-116">В Visual Studio в меню **файл** наведите указатель мыши на пункт **создать** и выберите **проект**.</span><span class="sxs-lookup"><span data-stu-id="3670b-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="3670b-117">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="3670b-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="3670b-118">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="3670b-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="3670b-119">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="3670b-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="3670b-120">Задайте файлу имя `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="3670b-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="3670b-121">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3670b-121">Click **Add**.</span></span> <span data-ttu-id="3670b-122">Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="3670b-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="3670b-123">Добавление хранимых процедур в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="3670b-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="3670b-124">В **Обозреватель сервера** / **Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="3670b-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="3670b-125">Разверните папку **Хранимые процедуры** .</span><span class="sxs-lookup"><span data-stu-id="3670b-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="3670b-126">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="3670b-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="3670b-127">Щелкните хранимую процедуру **продажи по году** и перетащите ее на правую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="3670b-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="3670b-128">Щелкните **десять самых дорогих** хранимых процедур продуктов, перетащите ее на правую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="3670b-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="3670b-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="3670b-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="3670b-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="3670b-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="3670b-131">Добавление кода для вывода результатов хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="3670b-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="3670b-132">Перетащите элемент управления из **области элементов**в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="3670b-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="3670b-133">Дважды щелкните Form1, чтобы добавить код к `Load` событию.</span><span class="sxs-lookup"><span data-stu-id="3670b-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="3670b-134">При добавлении хранимых процедур в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="3670b-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="3670b-135">Этот объект содержит код, который необходим для доступа к этим процедурам.</span><span class="sxs-lookup"><span data-stu-id="3670b-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="3670b-136">Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="3670b-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="3670b-137">Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="3670b-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="3670b-138">В коде можно создать экземпляр класса <xref:System.Data.Linq.DataContext> и вызвать методы хранимой процедуры, заданные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="3670b-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="3670b-139">Чтобы выполнить привязку к <xref:System.Windows.Forms.DataGridView> объекту, может потребоваться принудительно выполнить запрос, вызвав <xref:System.Linq.Enumerable.ToList%2A> метод для результатов хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="3670b-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="3670b-140">Добавьте следующий код в `Load` событие для вызова любой из хранимых процедур, предоставляемых как методы для контекста данных.</span><span class="sxs-lookup"><span data-stu-id="3670b-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="3670b-141">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="3670b-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3670b-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3670b-142">See also</span></span>

- [<span data-ttu-id="3670b-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="3670b-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="3670b-144">Запросы</span><span class="sxs-lookup"><span data-stu-id="3670b-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="3670b-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3670b-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="3670b-146">Методы DataContext (реляционный конструктор R)</span><span class="sxs-lookup"><span data-stu-id="3670b-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="3670b-147">Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="3670b-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
