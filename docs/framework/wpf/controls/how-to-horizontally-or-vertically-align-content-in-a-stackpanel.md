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
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали
В этом примере показано, как настроить <xref:System.Windows.Controls.StackPanel.Orientation%2A> содержимое в <xref:System.Windows.Controls.StackPanel> элементе, а также как настроить <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и для <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> дочернего содержимого.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются три <xref:System.Windows.Controls.ListBox> элемента в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Каждый из них <xref:System.Windows.Controls.ListBox> представляет возможные значения <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойств, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> объекта <xref:System.Windows.Controls.StackPanel> . Когда пользователь выбирает значение в любом из <xref:System.Windows.Controls.ListBox> элементов, изменяется связанное свойство элемента <xref:System.Windows.Controls.StackPanel> и его дочерние <xref:System.Windows.Controls.Button> элементы.  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Следующий файл кода программной части определяет изменения событий, связанных с <xref:System.Windows.Controls.ListBox> изменениями выбора. <xref:System.Windows.Controls.StackPanel>определяется <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [Общие сведения о панелях](panels-overview.md)
