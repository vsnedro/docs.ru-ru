---
title: Практическое руководство. Создание пользовательского режима представления для ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243223"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="bb646-102">Как: Создать пользовательский режим представления для ListView</span><span class="sxs-lookup"><span data-stu-id="bb646-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="bb646-103">В этом примере показано, как создать пользовательский <xref:System.Windows.Controls.ListView.View%2A> режим управления. <xref:System.Windows.Controls.ListView></span><span class="sxs-lookup"><span data-stu-id="bb646-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb646-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bb646-104">Example</span></span>  
 <span data-ttu-id="bb646-105">При создании <xref:System.Windows.Controls.ViewBase> пользовательского представления для элемента <xref:System.Windows.Controls.ListView> управления необходимо использовать класс.</span><span class="sxs-lookup"><span data-stu-id="bb646-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="bb646-106">В следующем примере показан `PlainView` режим представления, называемый полученным <xref:System.Windows.Controls.ViewBase> из класса.</span><span class="sxs-lookup"><span data-stu-id="bb646-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="bb646-107">Чтобы применить стиль к пользовательскому <xref:System.Windows.Style> представлению, используйте класс.</span><span class="sxs-lookup"><span data-stu-id="bb646-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="bb646-108">Следующий пример определяет <xref:System.Windows.Style> режим `PlainView` представления.</span><span class="sxs-lookup"><span data-stu-id="bb646-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="bb646-109">В предыдущем примере этот стиль устанавливается <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> как значение свойства, `PlainView`которое определено для.</span><span class="sxs-lookup"><span data-stu-id="bb646-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="bb646-110">Чтобы определить расположение данных в пользовательском режиме представления, определите <xref:System.Windows.DataTemplate> объект.</span><span class="sxs-lookup"><span data-stu-id="bb646-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="bb646-111">Следующий пример <xref:System.Windows.DataTemplate> определяет, который может быть использован `PlainView` для отображения данных в режиме представления.</span><span class="sxs-lookup"><span data-stu-id="bb646-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="bb646-112">В следующем примере показано, как определить <xref:System.Windows.ResourceKey> для режима `PlainView` представления, который <xref:System.Windows.DataTemplate> использует, который определен в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="bb646-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="bb646-113">Элемент <xref:System.Windows.Controls.ListView> управления может использовать пользовательское <xref:System.Windows.Controls.ListView.View%2A> представление, если настроить свойство на ключ ресурса.</span><span class="sxs-lookup"><span data-stu-id="bb646-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="bb646-114">В следующем примере `PlainView` показано, как указать режим представления для <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="bb646-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="bb646-115">Для полного примера см. [ListView с несколькими представлениями (C)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) или [ListView с несколькими представлениями (Visual Basic).](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)</span><span class="sxs-lookup"><span data-stu-id="bb646-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb646-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bb646-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="bb646-117">Инструкции</span><span class="sxs-lookup"><span data-stu-id="bb646-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="bb646-118">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="bb646-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="bb646-119">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="bb646-119">GridView Overview</span></span>](gridview-overview.md)
