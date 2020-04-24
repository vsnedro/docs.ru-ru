---
title: Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: 3b222880aa4eda32502e3dcece2fa5c0b57b7a51
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646436"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate
В этом примере показано, как <xref:System.Windows.DataTemplate>найти элементы, генерируемые .  
  
## <a name="example"></a>Пример  
 В этом примере <xref:System.Windows.Controls.ListBox> есть данные XML, связанные с некоторыми данными XML:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Использует <xref:System.Windows.Controls.ListBox> следующее: <xref:System.Windows.DataTemplate>  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Если вы хотите получить <xref:System.Windows.Controls.TextBlock> элемент, <xref:System.Windows.DataTemplate> генерируемый <xref:System.Windows.Controls.ListBoxItem>определенным, вам <xref:System.Windows.Controls.ListBoxItem> <xref:System.Windows.Controls.ContentPresenter> нужно получить, <xref:System.Windows.Controls.ListBoxItem>найти в <xref:System.Windows.FrameworkTemplate.FindName%2A> том, <xref:System.Windows.DataTemplate> что , <xref:System.Windows.Controls.ContentPresenter>а затем позвонить по тому, что установлено на этом. В следующем примере показано, как выполнять эти действия. Для демонстрационных целей этот пример создает поле сообщений, которое показывает текстовое содержимое <xref:System.Windows.DataTemplate>генерируемого текстового блока.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Ниже приводится реализация `FindVisualChild`, которая <xref:System.Windows.Media.VisualTreeHelper> использует методы:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Поиск элемента, созданного шаблоном ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Инструкции](data-binding-how-to-topics.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Области видимости имен XAML в WPF](../advanced/wpf-xaml-namescopes.md)
- [Деревья в WPF](../advanced/trees-in-wpf.md)
