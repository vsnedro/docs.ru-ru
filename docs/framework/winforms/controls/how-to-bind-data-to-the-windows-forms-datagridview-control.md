---
title: Привязка данных к элементу управления DataGridView
ms.date: 02/08/2019
description: Узнайте, как элемент управления DataGridView поддерживает стандартную модель привязки данных Windows Forms, чтобы она могла выполнять привязку к различным источникам данных.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 3c3502804d1bc4a5eeffc22b4ec5f2773411ef69
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904420"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="d3258-103">Как привязать данные к элементу управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="d3258-103">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="d3258-104"><xref:System.Windows.Forms.DataGridView>Элемент управления поддерживает стандартную модель привязки данных Windows Forms, поэтому она может выполнять привязку к различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="d3258-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="d3258-105">Как правило, привязка выполняется к элементу <xref:System.Windows.Forms.BindingSource> , который управляет взаимодействием с источником данных.</span><span class="sxs-lookup"><span data-stu-id="d3258-105">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="d3258-106"><xref:System.Windows.Forms.BindingSource>Может быть любым Windows Formsным источником данных, что обеспечивает большую гибкость при выборе или изменении расположения данных.</span><span class="sxs-lookup"><span data-stu-id="d3258-106">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="d3258-107">Дополнительные сведения о том, какие источники данных <xref:System.Windows.Forms.DataGridView> поддерживает элемент управления, см. в разделе [Общие сведения об элементе управления DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d3258-107">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="d3258-108">Visual Studio обладает расширенной поддержкой привязки данных к элементу управления DataGridView.</span><span class="sxs-lookup"><span data-stu-id="d3258-108">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="d3258-109">Дополнительные сведения см. в разделе [инструкции. Привязка данных к элементу управления Windows Forms DataGridView с помощью конструктора](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="d3258-109">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="d3258-110">Подключение элемента управления DataGridView к данным:</span><span class="sxs-lookup"><span data-stu-id="d3258-110">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="d3258-111">Реализуйте метод для управления деталями извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="d3258-111">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="d3258-112">В следующем примере кода реализуется `GetData` метод, который инициализирует <xref:System.Data.SqlClient.SqlDataAdapter> и использует его для заполнения <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="d3258-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d3258-113">Затем он привязывает <xref:System.Data.DataTable> к <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="d3258-113">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="d3258-114">В <xref:System.Windows.Forms.Form.Load> обработчике событий формы привяжите <xref:System.Windows.Forms.DataGridView> элемент управления к <xref:System.Windows.Forms.BindingSource> и вызовите `GetData` метод для получения данных.</span><span class="sxs-lookup"><span data-stu-id="d3258-114">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="d3258-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d3258-115">Example</span></span>

<span data-ttu-id="d3258-116">Этот полный пример кода извлекает данные из базы данных для заполнения элемента управления DataGridView в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3258-116">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="d3258-117">Форма также содержит кнопки для перезагрузки данных и отправки изменений в базу данных.</span><span class="sxs-lookup"><span data-stu-id="d3258-117">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="d3258-118">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d3258-118">This example requires:</span></span>

- <span data-ttu-id="d3258-119">Доступ к образцу базы данных Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3258-119">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="d3258-120">Дополнительные сведения об установке образца базы данных Northwind см. [в статье получение образцов баз данных для ADO.NET кода](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d3258-120">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

- <span data-ttu-id="d3258-121">Ссылки на системные сборки, System. Windows. Forms, System. Data и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="d3258-121">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="d3258-122">Чтобы выполнить сборку и запуск этого примера, вставьте код в файл кода *Form1* в новом Windows Forms проекте.</span><span class="sxs-lookup"><span data-stu-id="d3258-122">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="d3258-123">Сведения о построении из командной строки C# или Visual Basic см. в разделе Построение из командной строки [с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="d3258-123">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="d3258-124">Заполните `connectionString` переменную в примере значениями для образца подключения к базе данных Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3258-124">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="d3258-125">Проверка подлинности Windows, называемая также встроенной безопасностью, является более безопасным способом подключения к базе данных, чем сохранение пароля в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="d3258-125">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="d3258-126">Дополнительные сведения о безопасности подключения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="d3258-126">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d3258-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d3258-127">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d3258-128">Отображение данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="d3258-128">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d3258-129">Защита сведений о соединении</span><span class="sxs-lookup"><span data-stu-id="d3258-129">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
