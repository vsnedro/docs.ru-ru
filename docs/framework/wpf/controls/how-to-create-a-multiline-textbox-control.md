---
title: Как создать элемент управления для нескольких TextBox
description: Узнайте, как использовать XAML для определения элемента управления TextBox, который расширяется для размещения нескольких строк текста в Windows Presentation Foundation приложении.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166256"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Как создать элемент управления для нескольких TextBox
В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемента управления, который автоматически расширяется для размещения нескольких строк текста.  
  
## <a name="example"></a>Пример  
 Если задать <xref:System.Windows.Controls.TextBox.TextWrapping%2A> для атрибута значение **Wrap** , введенный текст будет переноситься в новую строку при <xref:System.Windows.Controls.TextBox> достижении края элемента управления, при необходимости автоматически расширяя <xref:System.Windows.Controls.TextBox> элемент управления, чтобы он включал в себя место для новой строки.  
  
 Присвоение <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибуту значения **true** приводит к вставке новой строки при нажатии клавиши Return, а также при необходимости автоматически расширять объект, <xref:System.Windows.Controls.TextBox> чтобы включить в него место для новой строки.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>Атрибут добавляет полосу прокрутки к <xref:System.Windows.Controls.TextBox> , что <xref:System.Windows.Controls.TextBox> позволяет прокручивать содержимое элемента, если <xref:System.Windows.Controls.TextBox> расширяется до размера фрейма или окна, в котором он находится.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.TextWrapping>
- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
