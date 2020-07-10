---
title: Общие сведения о TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 86b2cf8cb0c72186fd92bdad0af6bf5bd3fa9f3f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174436"
---
# <a name="textbox-overview"></a>Общие сведения о TextBox
<xref:System.Windows.Controls.TextBox>Класс позволяет отображать или редактировать неформатированный текст. Обычно используется для <xref:System.Windows.Controls.TextBox> редактирования неформатированного текста в форме. Например, форма, запрашивающая имя пользователя, номер телефона и т. д., будет использовать <xref:System.Windows.Controls.TextBox> элементы управления для ввода текста. В этом разделе описывается <xref:System.Windows.Controls.TextBox> класс и приводятся примеры его использования в и в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] C#.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>TextBox или RichTextBox?  
 <xref:System.Windows.Controls.TextBox>И, и <xref:System.Windows.Controls.RichTextBox> позволяют пользователям вводить текст, но два элемента управления используются в различных сценариях. Для <xref:System.Windows.Controls.TextBox> требуется меньше системных ресурсов, а <xref:System.Windows.Controls.RichTextBox> так далее, если требуется редактировать только обычный текст (т. е. использование в форме). Является <xref:System.Windows.Controls.RichTextBox> лучшим выбором, когда необходимо, чтобы пользователь изменяю форматированный текст, изображения, таблицы или другое поддерживаемое содержимое. Например, изменение документа, статьи или блога, для которого требуется форматирование, изображения и т. д., лучше всего выполнять с помощью <xref:System.Windows.Controls.RichTextBox> . В следующей таблице перечислены основные возможности <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> .  
  
|Элемент Control|Проверка орфографии в режиме реального времени|Контекстное меню|Команды форматирования, например <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctrl + B)|<xref:System.Windows.Documents.FlowDocument>содержимое, например изображения, абзацы, таблицы и т. д.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Да|Да|Нет|Нет.|  
|<xref:System.Windows.Controls.RichTextBox>|Да|Да|Да (см. раздел [Общие сведения о RichTextBox](richtextbox-overview.md))|Да (см. раздел [Общие сведения о RichTextBox](richtextbox-overview.md))|  
  
> [!NOTE]
> Хотя не <xref:System.Windows.Controls.TextBox> поддерживает форматирование, связанное с правками <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> , например (Ctrl + B), многие основные команды поддерживаются обоими элементами управления, такими как <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> . Дополнительные сведения см. в разделе <xref:System.Windows.Documents.EditingCommands>.  
  
 Функции, поддерживаемые <xref:System.Windows.Controls.TextBox> в, описаны в следующих разделах. Дополнительные сведения о см <xref:System.Windows.Controls.RichTextBox> . в разделе [Общие сведения о RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Проверка орфографии в режиме реального времени  
 Проверку орфографии в режиме реального времени можно включить в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox> . При включенной проверке орфографии все слова с ошибками подчеркиваются красной линией (см. рисунок ниже).  
  
 ![Текстовое поле с проверкой орфографии&#45;](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Чтобы научиться включать проверку правописания, см. раздел [Включение проверки орфографии в элементе управления редактирования текста](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Контекстное меню  
 По умолчанию <xref:System.Windows.Controls.TextBox> и, и <xref:System.Windows.Controls.RichTextBox> имеют контекстное меню, отображаемое, когда пользователь щелкает правой кнопкой мыши внутри элемента управления. Контекстное меню дает пользователю возможность вырезания, копирования и вставки (см. рисунок ниже).  
  
 ![TextBox с контекстным меню](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Можно создать собственное пользовательское контекстное меню, чтобы переопределить поведение по умолчанию. Дополнительные сведения см. в разделе [Использование пользовательского контекстного меню с элементом TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>Создание элементов TextBox  
 <xref:System.Windows.Controls.TextBox>Может быть одной строкой по высоте или состоять из нескольких строк. Одна строка <xref:System.Windows.Controls.TextBox> лучше подходит для вывода небольших объемов обычного текста (т. е. "имя", "номер телефона" и т. д. в форме). В следующем примере показано, как создать одну строку <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Можно также создать <xref:System.Windows.Controls.TextBox> , который позволяет пользователю вводить несколько строк текста. Например, если ваша форма запросила биографикал наброска пользователя, необходимо использовать объект <xref:System.Windows.Controls.TextBox> , поддерживающий несколько строк текста. В следующем примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемента управления, который автоматически расширяется для размещения нескольких строк текста.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Присвоение <xref:System.Windows.Controls.TextBox.TextWrapping%2A> атрибуту значения `Wrap` приводит к переносу текста на новую строку при <xref:System.Windows.Controls.TextBox> достижении края элемента управления, при необходимости автоматически расширяя <xref:System.Windows.Controls.TextBox> элемент управления, чтобы он включал в себя место для новой строки.  
  
 Если присвоить <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибуту значение `true` , то при нажатии клавиши возврата новая строка будет вставлена, а затем автоматически разворачиваться <xref:System.Windows.Controls.TextBox> для включения в нее места для новой строки.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>Атрибут добавляет полосу прокрутки к <xref:System.Windows.Controls.TextBox> , что <xref:System.Windows.Controls.TextBox> позволяет прокручивать содержимое элемента, если <xref:System.Windows.Controls.TextBox> расширяется до размера фрейма или окна, в котором он находится.  
  
 Дополнительные сведения о различных задачах, связанных с использованием <xref:System.Windows.Controls.TextBox> , см. [в разделах с инструкциями](textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>Определение изменения содержимого  
 Обычно <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> событие следует использовать для обнаружения изменений текста в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox> , а не в том виде, в <xref:System.Windows.UIElement.KeyDown> котором они могут ожидать. Пример см. в разделе [Определение изменения текста в TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>См. также раздел

- [Практические руководства](textbox-how-to-topics.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
