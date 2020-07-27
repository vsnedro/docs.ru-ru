---
title: Практическое руководство. Добавление обработчика событий с помощью кода
description: Используйте этот пример, чтобы узнать, как добавить обработчик событий к элементу в Windows Presentation Foundation с помощью кода, а не объявлять его с помощью XAML.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166374"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="dea46-103">Практическое руководство. Добавление обработчика событий с помощью кода</span><span class="sxs-lookup"><span data-stu-id="dea46-103">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="dea46-104">В этом примере показано, как добавить обработчик событий в элемент с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="dea46-104">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="dea46-105">Если необходимо добавить обработчик событий к [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементу, а страница разметки, содержащая этот элемент, уже загружена, необходимо добавить обработчик с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="dea46-105">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="dea46-106">Кроме того, если вы создаете дерево элементов для приложения полностью с помощью кода и не объявляете какие бы то ни было элементы с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , можно вызывать определенные методы для добавления обработчиков событий в сконструированное дерево элементов.</span><span class="sxs-lookup"><span data-stu-id="dea46-106">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dea46-107">Пример</span><span class="sxs-lookup"><span data-stu-id="dea46-107">Example</span></span>  
 <span data-ttu-id="dea46-108">В следующем примере добавляется новый объект <xref:System.Windows.Controls.Button> в существующую страницу, которая изначально определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dea46-108">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="dea46-109">Файл кода программной части реализует метод обработчика событий, а затем добавляет этот метод в качестве нового обработчика событий в <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="dea46-109">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="dea46-110">В примере C# оператор используется `+=` для назначения обработчика событию.</span><span class="sxs-lookup"><span data-stu-id="dea46-110">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="dea46-111">Это тот же оператор, который используется для назначения обработчика в модели обработки событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dea46-111">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="dea46-112">Microsoft Visual Basic не поддерживает этот оператор как средство добавления обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="dea46-112">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="dea46-113">Вместо этого требуется один из двух методов:</span><span class="sxs-lookup"><span data-stu-id="dea46-113">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="dea46-114">Используйте <xref:System.Windows.UIElement.AddHandler%2A> метод вместе с `AddressOf` оператором для ссылки на реализацию обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="dea46-114">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="dea46-115">Используйте `Handles` ключевое слово как часть определения обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="dea46-115">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="dea46-116">Этот метод не показан здесь; см. раздел [Обработка событий Visual Basic и WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="dea46-116">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="dea46-117">Добавление обработчика событий на странице изначально проанализировано [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] гораздо проще.</span><span class="sxs-lookup"><span data-stu-id="dea46-117">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="dea46-118">В элементе Object, куда нужно добавить обработчик событий, добавьте атрибут, соответствующий имени события, которое необходимо обменять.</span><span class="sxs-lookup"><span data-stu-id="dea46-118">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="dea46-119">Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенного в файле кода программной части [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="dea46-119">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="dea46-120">Дополнительные сведения см. в разделе Общие сведения [о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) или [перенаправленные события](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dea46-120">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea46-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dea46-121">See also</span></span>

- [<span data-ttu-id="dea46-122">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="dea46-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="dea46-123">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="dea46-123">How-to Topics</span></span>](events-how-to-topics.md)
