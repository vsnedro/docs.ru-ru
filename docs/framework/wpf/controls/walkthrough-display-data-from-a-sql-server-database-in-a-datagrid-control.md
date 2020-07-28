---
title: Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid
description: Узнайте, как получать данные из базы данных SQL Server и отображать их в элементе управления Windows Presentation Foundation DataGrid с помощью этого пошагового руководства.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: cc41979c869021c9c363f3f68ce590d4702e068c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167556"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="22396-103">Пошаговое руководство. Отображение данных из SQL Server базы данных в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="22396-103">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="22396-104">В этом пошаговом руководстве вы получаете данные из базы данных SQL Server и отображает их в <xref:System.Windows.Controls.DataGrid> элементе управления.</span><span class="sxs-lookup"><span data-stu-id="22396-104">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="22396-105">Entity Framework ADO.NET используется для создания классов сущностей, представляющих данные, и использования LINQ для написания запроса, который извлекает указанные данные из класса сущностей.</span><span class="sxs-lookup"><span data-stu-id="22396-105">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22396-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="22396-106">Prerequisites</span></span>

<span data-ttu-id="22396-107">Для выполнения этого пошагового руководства требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="22396-107">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="22396-108">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="22396-108">Visual Studio.</span></span>

- <span data-ttu-id="22396-109">Доступ к выполняющемуся экземпляру SQL Server или SQL Server Express, к которому присоединен образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="22396-109">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="22396-110">Базу данных AdventureWorks можно загрузить с сайта [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="22396-110">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="22396-111">Создание классов сущностей</span><span class="sxs-lookup"><span data-stu-id="22396-111">Create entity classes</span></span>

1. <span data-ttu-id="22396-112">Создайте новый проект приложения WPF в Visual Basic или C# и присвойте ему имя `DataGridSQLExample` .</span><span class="sxs-lookup"><span data-stu-id="22396-112">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="22396-113">В обозреватель решений щелкните правой кнопкой мыши проект, наведите указатель на пункт **Добавить**и выберите пункт **создать элемент**.</span><span class="sxs-lookup"><span data-stu-id="22396-113">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="22396-114">Откроется диалоговое окно Добавить новый элемент.</span><span class="sxs-lookup"><span data-stu-id="22396-114">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="22396-115">В области Установленные шаблоны выберите **данные** и в списке шаблонов выберите **ADO.NET EDM**.</span><span class="sxs-lookup"><span data-stu-id="22396-115">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![Шаблон элемента EDM ADO.NET](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="22396-117">Присвойте файлу имя `AdventureWorksModel.edmx` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="22396-117">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="22396-118">Появится мастер модели EDM.</span><span class="sxs-lookup"><span data-stu-id="22396-118">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="22396-119">На экране Выбор содержимого модели выберите **конструктор EF из базы данных** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="22396-119">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="22396-120">На экране Выбор подключения к данным укажите подключение к базе данных AdventureWorksLT2008.</span><span class="sxs-lookup"><span data-stu-id="22396-120">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="22396-121">Дополнительные сведения см. в разделе [диалоговое окно "Выбор подключения к данным"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="22396-121">For more information, see [Choose Your Data Connection Dialog Box](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span></span>

    <span data-ttu-id="22396-122">Убедитесь, что имя имеет значение, `AdventureWorksLT2008Entities` а флажок **сохранить параметры подключения сущности в App.Config как** установлен, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="22396-122">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="22396-123">На экране Выбор объектов базы данных разверните узел таблицы и выберите таблицы **Product** и **ProductCategory** .</span><span class="sxs-lookup"><span data-stu-id="22396-123">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="22396-124">Можно создавать классы сущностей для всех таблиц. Однако в этом примере данные извлекаются только из этих двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="22396-124">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="22396-125">![Выбор пунктов Product и ProductCategory из таблиц](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="22396-125">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="22396-126">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="22396-126">Click **Finish**.</span></span>

     <span data-ttu-id="22396-127">Сущности Product и ProductCategory отображаются в Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="22396-127">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="22396-128">![Модели сущностей Product и ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="22396-128">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="22396-129">Получение и представление данных</span><span class="sxs-lookup"><span data-stu-id="22396-129">Retrieve and present the data</span></span>

1. <span data-ttu-id="22396-130">Откройте файл MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="22396-130">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="22396-131">Установите свойство в значение <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Window> 450.</span><span class="sxs-lookup"><span data-stu-id="22396-131">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="22396-132">В редакторе XAML добавьте следующий <xref:System.Windows.Controls.DataGrid> тег между `<Grid>` тегами и, `</Grid>` чтобы добавить <xref:System.Windows.Controls.DataGrid> именованный объект `dataGrid1` .</span><span class="sxs-lookup"><span data-stu-id="22396-132">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="22396-133">![Окно с DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="22396-133">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="22396-134">Выберите <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="22396-134">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="22396-135">С помощью окно свойств или редактора XAML Создайте обработчик событий для <xref:System.Windows.Window> именованного `Window_Loaded` <xref:System.Windows.FrameworkElement.Loaded> события.</span><span class="sxs-lookup"><span data-stu-id="22396-135">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="22396-136">Дополнительные сведения см. [в разделе инструкции. Создание простого обработчика событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="22396-136">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="22396-137">Ниже показан XAML для MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="22396-137">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="22396-138">При использовании Visual Basic в первой строке файла MainWindow. XAML замените на `x:Class="DataGridSQLExample.MainWindow"` `x:Class="MainWindow"` .</span><span class="sxs-lookup"><span data-stu-id="22396-138">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="22396-139">Откройте файл кода программной части (MainWindow. XAML. vb или MainWindow.xaml.cs) для <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="22396-139">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="22396-140">Добавьте следующий код, чтобы получить только определенные значения из соединяемых таблиц и задать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для свойства объекта <xref:System.Windows.Controls.DataGrid> результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="22396-140">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="22396-141">Запустите пример.</span><span class="sxs-lookup"><span data-stu-id="22396-141">Run the example.</span></span>

     <span data-ttu-id="22396-142">Вы увидите <xref:System.Windows.Controls.DataGrid> , что отображает данные.</span><span class="sxs-lookup"><span data-stu-id="22396-142">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="22396-143">![DataGrid с данными из базы данных SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="22396-143">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="22396-144">См. также</span><span class="sxs-lookup"><span data-stu-id="22396-144">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
