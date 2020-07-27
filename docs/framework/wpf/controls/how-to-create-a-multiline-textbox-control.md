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
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="e80a6-103">Как создать элемент управления для нескольких TextBox</span><span class="sxs-lookup"><span data-stu-id="e80a6-103">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="e80a6-104">В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемента управления, который автоматически расширяется для размещения нескольких строк текста.</span><span class="sxs-lookup"><span data-stu-id="e80a6-104">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e80a6-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e80a6-105">Example</span></span>  
 <span data-ttu-id="e80a6-106">Если задать <xref:System.Windows.Controls.TextBox.TextWrapping%2A> для атрибута значение **Wrap** , введенный текст будет переноситься в новую строку при <xref:System.Windows.Controls.TextBox> достижении края элемента управления, при необходимости автоматически расширяя <xref:System.Windows.Controls.TextBox> элемент управления, чтобы он включал в себя место для новой строки.</span><span class="sxs-lookup"><span data-stu-id="e80a6-106">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="e80a6-107">Присвоение <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибуту значения **true** приводит к вставке новой строки при нажатии клавиши Return, а также при необходимости автоматически расширять объект, <xref:System.Windows.Controls.TextBox> чтобы включить в него место для новой строки.</span><span class="sxs-lookup"><span data-stu-id="e80a6-107">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="e80a6-108"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>Атрибут добавляет полосу прокрутки к <xref:System.Windows.Controls.TextBox> , что <xref:System.Windows.Controls.TextBox> позволяет прокручивать содержимое элемента, если <xref:System.Windows.Controls.TextBox> расширяется до размера фрейма или окна, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="e80a6-108">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="e80a6-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e80a6-109">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="e80a6-110">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="e80a6-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="e80a6-111">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e80a6-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
