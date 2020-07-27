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
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="e92fb-103">Инструкция по Использованию SelectedValue, SelectedValuePath и SelectedItem</span><span class="sxs-lookup"><span data-stu-id="e92fb-103">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="e92fb-104">В этом примере показано, как использовать <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Свойства и для указания значения для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> объекта <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="e92fb-104">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e92fb-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e92fb-105">Example</span></span>  
 <span data-ttu-id="e92fb-106"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>Свойство предоставляет способ указания <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> в <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="e92fb-106">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="e92fb-107"><xref:System.Windows.Controls.TreeView.SelectedItem%2A>Представляет объект в <xref:System.Windows.Controls.ItemsControl.Items%2A> коллекции и <xref:System.Windows.Controls.TreeView> отображает значение отдельного свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="e92fb-107">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="e92fb-108"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>Свойство определяет путь к свойству, которое используется для определения значения <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="e92fb-108">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="e92fb-109">Примеры в этом разделе иллюстрируют эту концепцию.</span><span class="sxs-lookup"><span data-stu-id="e92fb-109">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="e92fb-110">В следующем примере показан объект <xref:System.Windows.Data.XmlDataProvider> , содержащий сведения о сотрудниках.</span><span class="sxs-lookup"><span data-stu-id="e92fb-110">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="e92fb-111">В следующем примере определяется объект <xref:System.Windows.HierarchicalDataTemplate> , который отображает `EmployeeName` и `EmployeeWorkDay` объекта `Employee` .</span><span class="sxs-lookup"><span data-stu-id="e92fb-111">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="e92fb-112">Обратите внимание, что не <xref:System.Windows.HierarchicalDataTemplate> указывает `EmployeeNumber` как часть шаблона.</span><span class="sxs-lookup"><span data-stu-id="e92fb-112">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="e92fb-113">В следующем примере показан объект <xref:System.Windows.Controls.TreeView> , который использует ранее определенный объект <xref:System.Windows.HierarchicalDataTemplate> и, который задает <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для свойства значение `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="e92fb-113">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="e92fb-114">При выборе `EmployeeName` в <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> свойство возвращает `EmployeeInfo` элемент данных, соответствующий выбранному `EmployeeName` .</span><span class="sxs-lookup"><span data-stu-id="e92fb-114">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="e92fb-115">Однако, поскольку для <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> этого параметра <xref:System.Windows.Controls.TreeView> задано значение `EmployeeNumber` , для свойства <xref:System.Windows.Controls.TreeView.SelectedValue%2A> задается значение `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="e92fb-115">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="e92fb-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e92fb-116">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="e92fb-117">Обзор элемента управления "TreeView"</span><span class="sxs-lookup"><span data-stu-id="e92fb-117">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="e92fb-118">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="e92fb-118">How-to Topics</span></span>](treeview-how-to-topics.md)
