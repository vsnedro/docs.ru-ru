---
title: Практическое руководство. Добавление сведений о строках в элемент управления DataGrid
description: Сведения о настройке представления данных при использовании элемента управления Windows Presentation Foundation DataGrid путем добавления раздела сведений о строке.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 8fd6b07f454681a0eed70d7a6208cfcc426dc920
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164956"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="f0195-103">Практическое руководство. Добавление сведений о строках в элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="f0195-103">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="f0195-104">При использовании <xref:System.Windows.Controls.DataGrid> элемента управления можно настроить представление данных, добавив раздел сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="f0195-104">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="f0195-105">Добавление раздела сведений о строке позволяет сгруппировать некоторые данные в шаблон, который можно показать или свернуть.</span><span class="sxs-lookup"><span data-stu-id="f0195-105">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="f0195-106">Например, можно добавить в коллекцию сведения о строках <xref:System.Windows.Controls.DataGrid> , представляющие только сводку по данным для каждой строки в <xref:System.Windows.Controls.DataGrid> , но при этом будет представлено больше полей данных, когда пользователь выбирает строку.</span><span class="sxs-lookup"><span data-stu-id="f0195-106">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="f0195-107">Вы определяете шаблон для раздела сведения о строке в <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойстве.</span><span class="sxs-lookup"><span data-stu-id="f0195-107">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="f0195-108">На следующем рисунке показан пример раздела сведений о строке.</span><span class="sxs-lookup"><span data-stu-id="f0195-108">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="f0195-109">![Сетка DataGrid, показанная со сведениями в строке](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="f0195-109">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="f0195-110">Шаблон сведений о строках определяется как встроенный XAML или ресурс.</span><span class="sxs-lookup"><span data-stu-id="f0195-110">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="f0195-111">Оба подхода показаны в следующих процедурах.</span><span class="sxs-lookup"><span data-stu-id="f0195-111">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="f0195-112">Шаблон данных, добавленный в качестве ресурса, можно использовать во всем проекте без повторного создания шаблона.</span><span class="sxs-lookup"><span data-stu-id="f0195-112">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="f0195-113">Шаблон данных, добавленный как встроенный код XAML, доступен только из элемента управления, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="f0195-113">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="f0195-114">Отображение сведений о строках с помощью встроенного кода XAML</span><span class="sxs-lookup"><span data-stu-id="f0195-114">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="f0195-115">Создайте объект <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="f0195-115">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="f0195-116">В элементе <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0195-116">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="f0195-117">Создайте объект <xref:System.Windows.DataTemplate> , определяющий внешний вид раздела сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="f0195-117">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="f0195-118">В следующем коде XAML показано <xref:System.Windows.Controls.DataGrid> и как определить <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> встроенное.</span><span class="sxs-lookup"><span data-stu-id="f0195-118">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="f0195-119">Объект <xref:System.Windows.Controls.DataGrid> отображает три значения в каждой строке и еще три значения при выборе строки.</span><span class="sxs-lookup"><span data-stu-id="f0195-119">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="f0195-120">В следующем коде показан запрос, который используется для выбора данных, отображаемых в <xref:System.Windows.Controls.DataGrid> .</span><span class="sxs-lookup"><span data-stu-id="f0195-120">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f0195-121">В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.</span><span class="sxs-lookup"><span data-stu-id="f0195-121">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="f0195-122">Отображение сведений о строках с помощью ресурса</span><span class="sxs-lookup"><span data-stu-id="f0195-122">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="f0195-123">Создайте объект <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="f0195-123">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="f0195-124">Добавьте <xref:System.Windows.FrameworkElement.Resources%2A> элемент в корневой элемент, например <xref:System.Windows.Window> элемент управления или <xref:System.Windows.Controls.Page> элемент управления, или добавьте <xref:System.Windows.Application.Resources%2A> элемент в <xref:System.Windows.Application> класс в файле App. XAML (или Application. XAML).</span><span class="sxs-lookup"><span data-stu-id="f0195-124">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="f0195-125">В элементе Resources создайте объект <xref:System.Windows.DataTemplate> , который определяет внешний вид раздела сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="f0195-125">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="f0195-126">В следующем коде XAML показан объект, <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> определенный в <xref:System.Windows.Application> классе.</span><span class="sxs-lookup"><span data-stu-id="f0195-126">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="f0195-127">В <xref:System.Windows.DataTemplate> присвойте [директиве x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) значение, уникально идентифицирующее шаблон данных.</span><span class="sxs-lookup"><span data-stu-id="f0195-127">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="f0195-128">В <xref:System.Windows.Controls.DataGrid> элементе задайте <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> для свойства ресурс, определенный на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="f0195-128">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="f0195-129">Назначьте ресурс как статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="f0195-129">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="f0195-130">В следующем коде XAML показано свойство, заданное <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> для ресурса из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="f0195-130">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="f0195-131">Установка видимости и предотвращение горизонтальной прокрутки для сведений о строках</span><span class="sxs-lookup"><span data-stu-id="f0195-131">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="f0195-132">При необходимости присвойте <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> свойству <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> значение.</span><span class="sxs-lookup"><span data-stu-id="f0195-132">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="f0195-133">По умолчанию устанавливается значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="f0195-133">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="f0195-134">Его можно задать для <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> отображения подробных сведений по всем строкам или <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> для скрытия сведений для всех строк.</span><span class="sxs-lookup"><span data-stu-id="f0195-134">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="f0195-135">При необходимости задайте для <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> свойства значение, `true` чтобы предотвратить горизонтальную прокрутку раздела сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="f0195-135">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
