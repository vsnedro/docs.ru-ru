---
title: Общие сведения об элементе управления ListView
description: Сведения о Windows Presentation Foundation элементе управления ListView, который предоставляет инфраструктуру для отображения элементов данных в различных макетах или представлениях.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 419c6216f0af696ec71e7607c79c2db637caa785
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164561"
---
# <a name="listview-overview"></a>Общие сведения об элементе управления ListView
<xref:System.Windows.Controls.ListView>Элемент управления предоставляет инфраструктуру для отображения набора элементов данных в различных макетах или представлениях. Например, у пользователя может возникнуть необходимость в отображении элементов данных в таблице, а также в сортировке ее столбцов.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>Понятие об элементе управления ListView  
 <xref:System.Windows.Controls.ListView>Элемент управления является <xref:System.Windows.Controls.ItemsControl> производным от <xref:System.Windows.Controls.ListBox> . Как правило, его элементы являются членами коллекции данных и представляются в виде <xref:System.Windows.Controls.ListViewItem> объектов. Объект <xref:System.Windows.Controls.ListViewItem> — <xref:System.Windows.Controls.ContentControl> и может содержать только один дочерний элемент. Но дочерним может быть любой визуальный элемент.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Определение режима представления для элемента управления ListView  
 Чтобы задать режим просмотра для содержимого <xref:System.Windows.Controls.ListView> элемента управления, необходимо задать <xref:System.Windows.Controls.ListView.View%2A> свойство. Один режим представления, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляющий <xref:System.Windows.Controls.GridView> коллекцию элементов данных в таблице с настраиваемыми столбцами.  
  
 В следующем примере показано, как определить <xref:System.Windows.Controls.GridView> для <xref:System.Windows.Controls.ListView> элемента управления, отображающего сведения о сотрудниках.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показано, как будут отображаться данные для предыдущего примера.  
  
 ![Снимок экрана, на котором показан ListView с выходными данными GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 Можно создать пользовательский режим представления, определив класс, наследующий от <xref:System.Windows.Controls.ViewBase> класса. <xref:System.Windows.Controls.ViewBase>Класс предоставляет инфраструктуру, необходимую для создания пользовательского представления. Дополнительные сведения о создании пользовательского представления см. в разделе [Создание пользовательского режима представления для ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Привязка данных к элементу управления ListView  
 Используйте <xref:System.Windows.Controls.ItemsControl.Items%2A> Свойства и, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> чтобы указать элементы для <xref:System.Windows.Controls.ListView> элемента управления. В следующем примере свойству присваивается значение <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> коллекции данных, которая называется `EmployeeInfoDataSource` .  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 В <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn> объекты привязываются к указанным полям данных. В следующем примере объект привязывается <xref:System.Windows.Controls.GridViewColumn> к полю данных путем указания <xref:System.Windows.Data.Binding> для <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Свойства.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Также можно указать <xref:System.Windows.Data.Binding> как часть <xref:System.Windows.DataTemplate> определения, используемого для применения стиля к ячейкам в столбце. В следующем примере объект <xref:System.Windows.DataTemplate> , идентифицированный с помощью, <xref:System.Windows.ResourceKey> устанавливает <xref:System.Windows.Data.Binding> для <xref:System.Windows.Controls.GridViewColumn> . Обратите внимание, что в этом примере не определяется объект, <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> поскольку это переопределяет привязку, заданную параметром <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Задание стиля ListView, который реализует GridView  
 <xref:System.Windows.Controls.ListView>Элемент управления содержит <xref:System.Windows.Controls.ListViewItem> объекты, которые представляют отображаемые элементы данных. Можно использовать следующие свойства для определения содержимого и стиля элементов данных:  
  
- На <xref:System.Windows.Controls.ListView> элементе управления используйте <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> свойства, и <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> .  
  
- На <xref:System.Windows.Controls.ListViewItem> элементе управления используйте <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> Свойства и.  
  
 Чтобы избежать проблем с выравниванием между ячейками в <xref:System.Windows.Controls.GridView> , не используйте <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для задания свойств или добавления содержимого, влияющего на ширину элемента в <xref:System.Windows.Controls.ListView> . Например, проблемы выравнивания могут возникнуть при задании <xref:System.Windows.FrameworkElement.Margin%2A> свойства в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . Чтобы задать свойства или определить содержимое, влияющее на ширину элементов в <xref:System.Windows.Controls.GridView> , используйте свойства <xref:System.Windows.Controls.GridView> класса и связанные с ним классы, такие как <xref:System.Windows.Controls.GridViewColumn> .  
  
 Дополнительные сведения об использовании <xref:System.Windows.Controls.GridView> и сопутствующих классах см. в разделе [Общие сведения о GridView](gridview-overview.md).  
  
 Если определить <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListView> элемента управления, а также определить <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , необходимо включить его <xref:System.Windows.Controls.ContentPresenter> в стиль, <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> чтобы обеспечить правильную работу.  
  
 Не используйте <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Свойства и для <xref:System.Windows.Controls.ListView> содержимого, которое отображается с помощью <xref:System.Windows.Controls.GridView> . Чтобы задать выравнивание содержимого в столбце <xref:System.Windows.Controls.GridView> , определите <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Совместное использование одного режима представления  
 Два <xref:System.Windows.Controls.ListView> элемента управления не могут одновременно использовать один режим просмотра. При попытке использовать один режим просмотра с несколькими <xref:System.Windows.Controls.ListView> элементами управления возникает исключение.  
  
 Чтобы указать режим представления, который может одновременно использоваться более чем одним <xref:System.Windows.Controls.ListView> , используйте шаблоны или стили.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Создание пользовательского режима представления  
 Настраиваемые представления, такие как <xref:System.Windows.Controls.GridView> , являются производными от <xref:System.Windows.Controls.ViewBase> абстрактного класса, который предоставляет средства для отображения элементов данных, представленных в виде <xref:System.Windows.Controls.ListViewItem> объектов.
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Общие сведения о GridView](gridview-overview.md)
- [Практические руководства](listview-how-to-topics.md)
- [Элементы управления](../advanced/optimizing-performance-controls.md)
