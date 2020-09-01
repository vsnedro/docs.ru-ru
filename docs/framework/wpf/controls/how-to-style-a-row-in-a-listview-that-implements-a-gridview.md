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
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="0def5-102">Инструкция по Изменению стиля строки в ListView, который реализует GridView</span><span class="sxs-lookup"><span data-stu-id="0def5-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="0def5-103">В этом примере показано, как использовать стиль строки в <xref:System.Windows.Controls.ListView> элементе управления, который использует <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> режим.</span><span class="sxs-lookup"><span data-stu-id="0def5-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0def5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0def5-104">Example</span></span>  
 <span data-ttu-id="0def5-105">Можно задать стиль строки в <xref:System.Windows.Controls.ListView> элементе управления, задав <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0def5-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="0def5-106">Задайте стиль для элементов, представленных в виде <xref:System.Windows.Controls.ListViewItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="0def5-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="0def5-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Ссылается на <xref:System.Windows.Controls.ControlTemplate> объекты, используемые для вывода содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="0def5-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="0def5-108">Полный пример, из которого извлекаются следующие примеры, отображает коллекцию сведений о песне, которые хранятся в базе данных XML.</span><span class="sxs-lookup"><span data-stu-id="0def5-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="0def5-109">Каждая композиция в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки со сведениями о композиции.</span><span class="sxs-lookup"><span data-stu-id="0def5-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="0def5-110">В следующем примере показано, как определить <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих песни в коллекции песен.</span><span class="sxs-lookup"><span data-stu-id="0def5-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="0def5-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Ссылки на <xref:System.Windows.Controls.ControlTemplate> объекты, указывающие, как отображать строку сведений о песне.</span><span class="sxs-lookup"><span data-stu-id="0def5-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="0def5-112">В следующем примере показан объект <xref:System.Windows.Controls.ControlTemplate> , который добавляет текстовую строку `"Strongly Recommended"` в строку.</span><span class="sxs-lookup"><span data-stu-id="0def5-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="0def5-113">На этот шаблон имеется ссылка в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображается, если оценка песни имеет значение 5 (пять).</span><span class="sxs-lookup"><span data-stu-id="0def5-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="0def5-114"><xref:System.Windows.Controls.ControlTemplate>Включает <xref:System.Windows.Controls.GridViewRowPresenter> объект, который располагает содержимым строки в столбцах, как определено в <xref:System.Windows.Controls.GridView> режиме представления.</span><span class="sxs-lookup"><span data-stu-id="0def5-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="0def5-115">В следующем примере определяется <xref:System.Windows.Controls.GridView> .</span><span class="sxs-lookup"><span data-stu-id="0def5-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="0def5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0def5-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="0def5-117">Инструкции</span><span class="sxs-lookup"><span data-stu-id="0def5-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="0def5-118">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="0def5-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="0def5-119">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="0def5-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
