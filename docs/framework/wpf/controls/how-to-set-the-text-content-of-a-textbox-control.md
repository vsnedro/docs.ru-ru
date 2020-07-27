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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="84b6d-103">Практическое руководство. Установка текстового содержимого для элемента управления TextBox</span><span class="sxs-lookup"><span data-stu-id="84b6d-103">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="84b6d-104">В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.Text%2A> свойство для задания начального текстового содержимого <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="84b6d-104">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="84b6d-105">Несмотря на то, что в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] версии примера можно использовать `<TextBox.Text>` теги вокруг текста для каждого содержимого кнопки <xref:System.Windows.Controls.TextBox> , это не обязательно, так как <xref:System.Windows.Controls.TextBox> применяет <xref:System.Windows.Markup.ContentPropertyAttribute> атрибут к <xref:System.Windows.Controls.TextBox.Text%2A> свойству.</span><span class="sxs-lookup"><span data-stu-id="84b6d-105">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="84b6d-106">Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="84b6d-106">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="84b6d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="84b6d-107">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="84b6d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="84b6d-108">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="84b6d-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84b6d-109">See also</span></span>

- [<span data-ttu-id="84b6d-110">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="84b6d-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="84b6d-111">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="84b6d-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
