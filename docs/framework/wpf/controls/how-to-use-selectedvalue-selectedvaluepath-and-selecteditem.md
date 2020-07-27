---
title: Инструкция по Использованию SelectedValue, SelectedValuePath и SelectedItem
description: Узнайте, как использовать свойства SelectedValue и SelectedValuePath, чтобы указать значение для SelectedItem Windows Presentation Foundation TreeView.
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166282"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Инструкция по Использованию SelectedValue, SelectedValuePath и SelectedItem
В этом примере показано, как использовать <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Свойства и для указания значения для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> объекта <xref:System.Windows.Controls.TreeView> .  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>Свойство предоставляет способ указания <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> в <xref:System.Windows.Controls.TreeView> . <xref:System.Windows.Controls.TreeView.SelectedItem%2A>Представляет объект в <xref:System.Windows.Controls.ItemsControl.Items%2A> коллекции и <xref:System.Windows.Controls.TreeView> отображает значение отдельного свойства выбранного элемента. <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>Свойство определяет путь к свойству, которое используется для определения значения <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Свойства. Примеры в этом разделе иллюстрируют эту концепцию.  
  
 В следующем примере показан объект <xref:System.Windows.Data.XmlDataProvider> , содержащий сведения о сотрудниках.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 В следующем примере определяется объект <xref:System.Windows.HierarchicalDataTemplate> , который отображает `EmployeeName` и `EmployeeWorkDay` объекта `Employee` . Обратите внимание, что не <xref:System.Windows.HierarchicalDataTemplate> указывает `EmployeeNumber` как часть шаблона.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 В следующем примере показан объект <xref:System.Windows.Controls.TreeView> , который использует ранее определенный объект <xref:System.Windows.HierarchicalDataTemplate> и, который задает <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для свойства значение `EmployeeNumber` . При выборе `EmployeeName` в <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> свойство возвращает `EmployeeInfo` элемент данных, соответствующий выбранному `EmployeeName` . Однако, поскольку для <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> этого параметра <xref:System.Windows.Controls.TreeView> задано значение `EmployeeNumber` , для свойства <xref:System.Windows.Controls.TreeView.SelectedValue%2A> задается значение `EmployeeNumber` .  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Обзор элемента управления "TreeView"](treeview-overview.md)
- [Практические руководства](treeview-how-to-topics.md)
