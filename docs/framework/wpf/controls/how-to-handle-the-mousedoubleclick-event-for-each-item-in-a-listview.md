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
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="da5d2-102">Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView</span><span class="sxs-lookup"><span data-stu-id="da5d2-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="da5d2-103">Для обработки события для <xref:System.Windows.Controls.ListView>элемента в элементе необходимо <xref:System.Windows.Controls.ListViewItem>добавить обработчик события для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="da5d2-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="da5d2-104">Когда <xref:System.Windows.Controls.ListView> a связан с источником данных, вы явно <xref:System.Windows.Controls.ListViewItem>не создаете, но вы можете <xref:System.Windows.EventSetter> обрабатывать событие для <xref:System.Windows.Controls.ListViewItem>каждого элемента, добавляя в стиль .</span><span class="sxs-lookup"><span data-stu-id="da5d2-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da5d2-105">Пример</span><span class="sxs-lookup"><span data-stu-id="da5d2-105">Example</span></span>  
 <span data-ttu-id="da5d2-106">Следующий пример создает связанную <xref:System.Windows.Controls.ListView> с <xref:System.Windows.Style> данными и создает <xref:System.Windows.Controls.ListViewItem>для добавления обработчика событий к каждому из них.</span><span class="sxs-lookup"><span data-stu-id="da5d2-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="da5d2-107">Следующий пример обрабатывает <xref:System.Windows.Controls.Control.MouseDoubleClick> событие.</span><span class="sxs-lookup"><span data-stu-id="da5d2-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="da5d2-108">Хотя наиболее часто <xref:System.Windows.Controls.ListView> привязывается к источнику данных, можно использовать <xref:System.Windows.Controls.ListViewItem> стиль для добавления обработчика событий к каждому из них в несвязанном <xref:System.Windows.Controls.ListView> данных независимо от того, создаете ли вы <xref:System.Windows.Controls.ListViewItem>явно.</span><span class="sxs-lookup"><span data-stu-id="da5d2-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="da5d2-109">Для получения дополнительной информации о <xref:System.Windows.Controls.ListViewItem> явно <xref:System.Windows.Controls.ItemsControl>созданных элементах управления см.</span><span class="sxs-lookup"><span data-stu-id="da5d2-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5d2-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="da5d2-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="da5d2-111">Обзор связывания данных</span><span class="sxs-lookup"><span data-stu-id="da5d2-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="da5d2-112">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="da5d2-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="da5d2-113">Привязываться к данным XML с помощью XMLDataProvider и XPath-запросов</span><span class="sxs-lookup"><span data-stu-id="da5d2-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="da5d2-114">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="da5d2-114">ListView Overview</span></span>](listview-overview.md)
