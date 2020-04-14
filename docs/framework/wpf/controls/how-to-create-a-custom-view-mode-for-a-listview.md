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
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Как: Создать пользовательский режим представления для ListView

В этом примере показано, как создать пользовательский <xref:System.Windows.Controls.ListView.View%2A> режим управления. <xref:System.Windows.Controls.ListView>  
  
## <a name="example"></a>Пример  
 При создании <xref:System.Windows.Controls.ViewBase> пользовательского представления для элемента <xref:System.Windows.Controls.ListView> управления необходимо использовать класс. В следующем примере показан `PlainView` режим представления, называемый полученным <xref:System.Windows.Controls.ViewBase> из класса.  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Чтобы применить стиль к пользовательскому <xref:System.Windows.Style> представлению, используйте класс. Следующий пример определяет <xref:System.Windows.Style> режим `PlainView` представления. В предыдущем примере этот стиль устанавливается <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> как значение свойства, `PlainView`которое определено для.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Чтобы определить расположение данных в пользовательском режиме представления, определите <xref:System.Windows.DataTemplate> объект. Следующий пример <xref:System.Windows.DataTemplate> определяет, который может быть использован `PlainView` для отображения данных в режиме представления.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 В следующем примере показано, как определить <xref:System.Windows.ResourceKey> для режима `PlainView` представления, который <xref:System.Windows.DataTemplate> использует, который определен в предыдущем примере.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Элемент <xref:System.Windows.Controls.ListView> управления может использовать пользовательское <xref:System.Windows.Controls.ListView.View%2A> представление, если настроить свойство на ключ ресурса. В следующем примере `PlainView` показано, как указать режим представления для <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Для полного примера см. [ListView с несколькими представлениями (C)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) или [ListView с несколькими представлениями (Visual Basic).](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Инструкции](listview-how-to-topics.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
- [Общие сведения о GridView](gridview-overview.md)
