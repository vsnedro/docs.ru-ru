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
# <a name="how-to-add-an-event-handler-using-code"></a>Практическое руководство. Добавление обработчика событий с помощью кода
В этом примере показано, как добавить обработчик событий в элемент с помощью кода.  
  
 Если необходимо добавить обработчик событий к [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементу, а страница разметки, содержащая этот элемент, уже загружена, необходимо добавить обработчик с помощью кода. Кроме того, если вы создаете дерево элементов для приложения полностью с помощью кода и не объявляете какие бы то ни было элементы с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , можно вызывать определенные методы для добавления обработчиков событий в сконструированное дерево элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере добавляется новый объект <xref:System.Windows.Controls.Button> в существующую страницу, которая изначально определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Файл кода программной части реализует метод обработчика событий, а затем добавляет этот метод в качестве нового обработчика событий в <xref:System.Windows.Controls.Button> .  
  
 В примере C# оператор используется `+=` для назначения обработчика событию. Это тот же оператор, который используется для назначения обработчика в модели обработки событий среды CLR. Microsoft Visual Basic не поддерживает этот оператор как средство добавления обработчиков событий. Вместо этого требуется один из двух методов:  
  
- Используйте <xref:System.Windows.UIElement.AddHandler%2A> метод вместе с `AddressOf` оператором для ссылки на реализацию обработчика событий.  
  
- Используйте `Handles` ключевое слово как часть определения обработчика событий. Этот метод не показан здесь; см. раздел [Обработка событий Visual Basic и WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Добавление обработчика событий на странице изначально проанализировано [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] гораздо проще. В элементе Object, куда нужно добавить обработчик событий, добавьте атрибут, соответствующий имени события, которое необходимо обменять. Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенного в файле кода программной части [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы. Дополнительные сведения см. в разделе Общие сведения [о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) или [перенаправленные события](routed-events-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
- [Практические руководства](events-how-to-topics.md)
