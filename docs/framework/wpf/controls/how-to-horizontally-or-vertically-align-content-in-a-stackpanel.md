---
title: Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали
description: Узнайте, как настроить ориентацию содержимого в Windows Presentation Foundation StackPanel, а также HorizontalAlignment и VerticalAlignment дочернего содержимого.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: d3c7215d8193d1d8a72597c44cf265f5bd400ea1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167630"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="1c933-103">Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали</span><span class="sxs-lookup"><span data-stu-id="1c933-103">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="1c933-104">В этом примере показано, как настроить <xref:System.Windows.Controls.StackPanel.Orientation%2A> содержимое в <xref:System.Windows.Controls.StackPanel> элементе, а также как настроить <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и для <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> дочернего содержимого.</span><span class="sxs-lookup"><span data-stu-id="1c933-104">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c933-105">Пример</span><span class="sxs-lookup"><span data-stu-id="1c933-105">Example</span></span>  
 <span data-ttu-id="1c933-106">В следующем примере создаются три <xref:System.Windows.Controls.ListBox> элемента в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c933-106">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="1c933-107">Каждый из них <xref:System.Windows.Controls.ListBox> представляет возможные значения <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойств, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> объекта <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="1c933-107">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="1c933-108">Когда пользователь выбирает значение в любом из <xref:System.Windows.Controls.ListBox> элементов, изменяется связанное свойство элемента <xref:System.Windows.Controls.StackPanel> и его дочерние <xref:System.Windows.Controls.Button> элементы.</span><span class="sxs-lookup"><span data-stu-id="1c933-108">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="1c933-109">Следующий файл кода программной части определяет изменения событий, связанных с <xref:System.Windows.Controls.ListBox> изменениями выбора.</span><span class="sxs-lookup"><span data-stu-id="1c933-109">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="1c933-110"><xref:System.Windows.Controls.StackPanel>определяется <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .</span><span class="sxs-lookup"><span data-stu-id="1c933-110"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1c933-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c933-111">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="1c933-112">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="1c933-112">Panels Overview</span></span>](panels-overview.md)
