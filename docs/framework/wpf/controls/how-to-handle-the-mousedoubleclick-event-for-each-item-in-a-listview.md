---
title: Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646109"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
Для обработки события для <xref:System.Windows.Controls.ListView>элемента в элементе необходимо <xref:System.Windows.Controls.ListViewItem>добавить обработчик события для каждого из них. Когда <xref:System.Windows.Controls.ListView> a связан с источником данных, вы явно <xref:System.Windows.Controls.ListViewItem>не создаете, но вы можете <xref:System.Windows.EventSetter> обрабатывать событие для <xref:System.Windows.Controls.ListViewItem>каждого элемента, добавляя в стиль .  
  
## <a name="example"></a>Пример  
 Следующий пример создает связанную <xref:System.Windows.Controls.ListView> с <xref:System.Windows.Style> данными и создает <xref:System.Windows.Controls.ListViewItem>для добавления обработчика событий к каждому из них.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Следующий пример обрабатывает <xref:System.Windows.Controls.Control.MouseDoubleClick> событие.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Хотя наиболее часто <xref:System.Windows.Controls.ListView> привязывается к источнику данных, можно использовать <xref:System.Windows.Controls.ListViewItem> стиль для добавления обработчика событий к каждому из них в несвязанном <xref:System.Windows.Controls.ListView> данных независимо от того, создаете ли вы <xref:System.Windows.Controls.ListViewItem>явно.  Для получения дополнительной информации о <xref:System.Windows.Controls.ListViewItem> явно <xref:System.Windows.Controls.ItemsControl>созданных элементах управления см.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.XmlElement>
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Привязываться к данным XML с помощью XMLDataProvider и XPath-запросов](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
