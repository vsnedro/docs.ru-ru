---
title: Как использовать стиль строки в ListView, использующем GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271949"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Инструкция по Изменению стиля строки в ListView, который реализует GridView
В этом примере показано, как использовать стиль строки в <xref:System.Windows.Controls.ListView> элементе управления, который использует <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> режим.  
  
## <a name="example"></a>Пример  
 Можно задать стиль строки в <xref:System.Windows.Controls.ListView> элементе управления, задав <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListView> элемента управления. Задайте стиль для элементов, представленных в виде <xref:System.Windows.Controls.ListViewItem> объектов. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Ссылается на <xref:System.Windows.Controls.ControlTemplate> объекты, используемые для вывода содержимого строки.  
  
 Полный пример, из которого извлекаются следующие примеры, отображает коллекцию сведений о песне, которые хранятся в базе данных XML. Каждая композиция в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки со сведениями о композиции.  
  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих песни в коллекции песен. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Ссылки на <xref:System.Windows.Controls.ControlTemplate> объекты, указывающие, как отображать строку сведений о песне.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 В следующем примере показан объект <xref:System.Windows.Controls.ControlTemplate> , который добавляет текстовую строку `"Strongly Recommended"` в строку. На этот шаблон имеется ссылка в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображается, если оценка песни имеет значение 5 (пять). <xref:System.Windows.Controls.ControlTemplate>Включает <xref:System.Windows.Controls.GridViewRowPresenter> объект, который располагает содержимым строки в столбцах, как определено в <xref:System.Windows.Controls.GridView> режиме представления.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 В следующем примере определяется <xref:System.Windows.Controls.GridView> .  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Инструкции](listview-how-to-topics.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
