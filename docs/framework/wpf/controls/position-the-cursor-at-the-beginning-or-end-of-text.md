---
title: Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox
description: Узнайте, как разместить курсор в начале или в конце текстового содержимого элемента управления TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: afe8b11d032b5d61fa91cbf324f02cd8415d2ea8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167510"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox
В этом примере показано, как разместить курсор в начале или в конце текстового содержимого <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Следующий [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] код описывает <xref:System.Windows.Controls.TextBox> элемент управления и присваивает ему имя.  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Пример  
 Чтобы поместить курсор в начало содержимого <xref:System.Windows.Controls.TextBox> элемента управления, вызовите <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию выбора 0 и длину выделения 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Пример  
 Чтобы поместить курсор в конец содержимого <xref:System.Windows.Controls.TextBox> элемента управления, вызовите <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию выбора, равную длине текстового содержимого, и длину выделения 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
