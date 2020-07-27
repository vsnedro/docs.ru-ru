---
title: Обзор элемента управления "TreeView"
description: Сведения о том, как элемент управления Windows Presentation Foundation TreeView отображает сведения в иерархической структуре с помощью узлов, в том числе простых примеров.
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 6ef77febdd3facb7c7e1af566841c2a1aeaff810
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164531"
---
# <a name="treeview-overview"></a>Обзор элемента управления "TreeView"
<xref:System.Windows.Controls.TreeView>Элемент управления позволяет отображать сведения в иерархической структуре с помощью свертываемых узлов. В этом разделе описываются <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeViewItem> элементы управления и, а также приводятся простые примеры их использования.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>Что такое элемент управления TreeView?  
 <xref:System.Windows.Controls.TreeView>— Это объект <xref:System.Windows.Controls.ItemsControl> , который вкладывает элементы с помощью <xref:System.Windows.Controls.TreeViewItem> элементов управления. В следующем примере создается объект <xref:System.Windows.Controls.TreeView> .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Создание элемента управления TreeView  
 <xref:System.Windows.Controls.TreeView>Элемент управления содержит иерархию <xref:System.Windows.Controls.TreeViewItem> элементов управления. <xref:System.Windows.Controls.TreeViewItem>Элемент управления — это объект <xref:System.Windows.Controls.HeaderedItemsControl> , который содержит <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> коллекцию и <xref:System.Windows.Controls.ItemsControl.Items%2A> .  
  
 При определении с помощью служб <xref:System.Windows.Controls.TreeView> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно явно определить <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> содержимое <xref:System.Windows.Controls.TreeViewItem> элемента управления и элементы, составляющие его коллекцию. Этот способ был показан на предыдущем рисунке.  
  
 Можно также указать в <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> качестве источника данных, а затем указать <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> и <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для определения <xref:System.Windows.Controls.TreeViewItem> содержимого.  
  
 Чтобы определить макет <xref:System.Windows.Controls.TreeViewItem> элемента управления, можно также использовать <xref:System.Windows.HierarchicalDataTemplate> объекты. Дополнительные сведения и пример см. в разделе [Использование свойств SelectedValue, SelectedValuePath и SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Если элемент не является <xref:System.Windows.Controls.TreeViewItem> элементом управления, он автоматически заключается в <xref:System.Windows.Controls.TreeViewItem> элемент управления при <xref:System.Windows.Controls.TreeView> отображении элемента управления.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Развертывание и свертывание элемента TreeViewItem  
 Если пользователь расширяет <xref:System.Windows.Controls.TreeViewItem> , свойство устанавливается в значение <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> `true` . Можно также развернуть или свернуть <xref:System.Windows.Controls.TreeViewItem> без прямого вмешательства пользователя, задав <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> для свойства значение `true` (развернуть) или `false` (свернуть). При изменении этого свойства <xref:System.Windows.Controls.TreeViewItem.Expanded> <xref:System.Windows.Controls.TreeViewItem.Collapsed> возникает событие или.  
  
 При <xref:System.Windows.FrameworkElement.BringIntoView%2A> вызове метода для <xref:System.Windows.Controls.TreeViewItem> элемента управления, <xref:System.Windows.Controls.TreeViewItem> и его родительские <xref:System.Windows.Controls.TreeViewItem> элементы управления расширяются. Если объект <xref:System.Windows.Controls.TreeViewItem> не является видимым или частично видимым, элемент <xref:System.Windows.Controls.TreeView> прокручивается, чтобы сделать его видимым.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Выбор элемента TreeViewItem  
 Когда пользователь щелкает <xref:System.Windows.Controls.TreeViewItem> элемент управления для его выбора, <xref:System.Windows.Controls.TreeViewItem.Selected> возникает событие, и его <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойство имеет значение `true` . Объект <xref:System.Windows.Controls.TreeViewItem> также превращается в <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> элемент управления. И наоборот, когда выбор изменяется из <xref:System.Windows.Controls.TreeViewItem> элемента управления, <xref:System.Windows.Controls.TreeViewItem.Unselected> происходит его событие, а его <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойство имеет значение `false` .  
  
 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>Свойство <xref:System.Windows.Controls.TreeView> элемента управления является свойством только для чтения, поэтому его нельзя задать явным образом. <xref:System.Windows.Controls.TreeView.SelectedItem%2A>Свойство задается, если пользователь щелкает <xref:System.Windows.Controls.TreeViewItem> элемент управления или если <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойство имеет значение `true` в <xref:System.Windows.Controls.TreeViewItem> элементе управления.  
  
 Используйте <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> свойство, чтобы указать для <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> . Подробнее см. в разделе [Использование свойств SelectedValue, SelectedValuePath и SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Можно зарегистрировать обработчик событий для <xref:System.Windows.Controls.TreeView.SelectedItemChanged> события, чтобы определить, когда выбрано <xref:System.Windows.Controls.TreeViewItem> изменение. Объект, <xref:System.Windows.RoutedPropertyChangedEventArgs%601> предоставляемый обработчику событий, задает объект <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> , который является предыдущим выделением, и объект <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> , который является текущим выделением. Каждое из этих значений может быть равно `null`, если ни предыдущий, ни текущий выбор не были сделаны ни пользователем, ни в приложении.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>Стиль элемента управления TreeView  
 Стиль по умолчанию для <xref:System.Windows.Controls.TreeView> элемента управления помещает его внутрь <xref:System.Windows.Controls.StackPanel> объекта, содержащего <xref:System.Windows.Controls.ScrollViewer> элемент управления. При задании <xref:System.Windows.FrameworkElement.Width%2A> свойств и <xref:System.Windows.FrameworkElement.Height%2A> для <xref:System.Windows.Controls.TreeView> , эти значения используются для изменения размера <xref:System.Windows.Controls.StackPanel> объекта, который отображает <xref:System.Windows.Controls.TreeView> . Если отображаемое содержимое больше, чем область отображения, <xref:System.Windows.Controls.ScrollViewer> автоматически отображается, чтобы пользователь мог прокручивать <xref:System.Windows.Controls.TreeView> содержимое.  
  
 Чтобы настроить внешний вид <xref:System.Windows.Controls.TreeViewItem> элемента управления, присвойте <xref:System.Windows.FrameworkElement.Style%2A> свойству значение Custom <xref:System.Windows.Style> .  
  
 В следующем примере показано, как задать <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> значения свойств и для <xref:System.Windows.Controls.TreeViewItem> элемента управления с помощью <xref:System.Windows.FrameworkElement.Style%2A> .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Добавление изображений и другого содержимого в элемент управления TreeView  
 В содержимое можно включить более одного объекта <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> . Чтобы включить в содержимое несколько объектов <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> , заключите эти объекты в элемент управления макет, например <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.StackPanel> .  
  
 В следующем примере показано, как определить объект <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> как <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.TextBlock> , заключенный в <xref:System.Windows.Controls.DockPanel> элемент управления.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 В следующем примере показано, как определить объект <xref:System.Windows.DataTemplate> , содержащий объект <xref:System.Windows.Controls.Image> и <xref:System.Windows.Controls.TextBlock> , который заключен в <xref:System.Windows.Controls.DockPanel> элемент управления. Можно использовать <xref:System.Windows.DataTemplate> для задания <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> или <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для <xref:System.Windows.Controls.TreeViewItem> .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Практические руководства](treeview-how-to-topics.md)
- [Модель содержимого WPF](wpf-content-model.md)
