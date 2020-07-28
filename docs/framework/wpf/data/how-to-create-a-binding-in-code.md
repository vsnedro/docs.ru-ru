---
title: Практическое руководство. Создание привязки в коде
description: Узнайте, как создать привязку в коде приложения Windows Presentation Foundation, вызвав метод SetBinding напрямую.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165808"
---
# <a name="how-to-create-a-binding-in-code"></a>Практическое руководство. Создание привязки в коде
В этом примере показано, как создать и задать <xref:System.Windows.Data.Binding> в коде.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.FrameworkElement>Класс и <xref:System.Windows.FrameworkContentElement> класс предоставляют `SetBinding` метод. При привязке элемента, который наследует любой из этих классов, можно вызвать <xref:System.Windows.FrameworkElement.SetBinding%2A> метод напрямую.  
  
 В следующем примере создается класс с именем, `MyData` , который содержит свойство с именем `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 В следующем примере показано, как создать объект привязки для задания источника привязки.  В примере используется <xref:System.Windows.FrameworkElement.SetBinding%2A> для привязки <xref:System.Windows.Controls.TextBlock.Text%2A> свойства `myText` , которое является <xref:System.Windows.Controls.TextBlock> элементом управления, к `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Полный пример кода см. в разделе [Пример привязки только для кода](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Вместо вызова <xref:System.Windows.FrameworkElement.SetBinding%2A> можно использовать <xref:System.Windows.Data.BindingOperations.SetBinding%2A> статический метод <xref:System.Windows.Data.BindingOperations> класса. В следующем примере вызывается <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> вместо <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> для привязки к `myText` `myDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
