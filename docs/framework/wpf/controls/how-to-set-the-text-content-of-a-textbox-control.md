---
title: Практическое руководство. Установка текстового содержимого для элемента управления TextBox
description: Узнайте, как использовать свойство Text для установки исходного текстового содержимого элемента управления TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 41efb69e297b3c6fdb1203c358dcc72d7a9f806f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168045"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Практическое руководство. Установка текстового содержимого для элемента управления TextBox

В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.Text%2A> свойство для задания начального текстового содержимого <xref:System.Windows.Controls.TextBox> элемента управления.

> [!NOTE]
> Несмотря на то, что в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] версии примера можно использовать `<TextBox.Text>` теги вокруг текста для каждого содержимого кнопки <xref:System.Windows.Controls.TextBox> , это не обязательно, так как <xref:System.Windows.Controls.TextBox> применяет <xref:System.Windows.Markup.ContentPropertyAttribute> атрибут к <xref:System.Windows.Controls.TextBox.Text%2A> свойству. Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Пример

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Пример

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>См. также раздел

- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
