---
title: Общие сведения о RichTextBox
description: Узнайте, как элемент управления Windows Presentation Foundation RichTextBox позволяет пользователям отображать или изменять содержимое, например текст, изображения и таблицы. См. примеры XAML и C#.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 525e27f9602136c68f160c738fd1c92ea761536c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166235"
---
# <a name="richtextbox-overview"></a>Общие сведения о RichTextBox

<xref:System.Windows.Controls.RichTextBox>Элемент управления позволяет отображать или редактировать содержимое нефиксированного формата, включая абзацы, изображения, таблицы и т. д. В этом разделе описывается <xref:System.Windows.Controls.TextBox> класс и приводятся примеры его использования в и в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] C#.

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a>TextBox или RichTextBox?

<xref:System.Windows.Controls.RichTextBox>И, и <xref:System.Windows.Controls.TextBox> позволяют пользователям редактировать текст, однако эти два элемента управления используются в различных сценариях. Является <xref:System.Windows.Controls.RichTextBox> лучшим выбором, когда необходимо, чтобы пользователь изменяю форматированный текст, изображения, таблицы или другое насыщенное содержимое. Например, изменение документа, статьи или блога, для которого требуется форматирование, изображения и т. д., лучше всего выполнять с помощью <xref:System.Windows.Controls.RichTextBox> . А <xref:System.Windows.Controls.TextBox> требует меньше системных ресурсов, <xref:System.Windows.Controls.RichTextBox> а и идеально подходит, когда требуется редактировать только обычный текст (т. е. использование в формах). Дополнительные сведения о см. в разделе [Обзор текстового поля](textbox-overview.md) <xref:System.Windows.Controls.TextBox> . В следующей таблице перечислены основные возможности <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> .

|Control|Проверка орфографии в режиме реального времени|Контекстное меню|Команды форматирования, например <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctrl + B)|<xref:System.Windows.Documents.FlowDocument>содержимое, например изображения, абзацы, таблицы и т. д.|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|да|Да|Нет|Нет.|
|<xref:System.Windows.Controls.RichTextBox>|да|да|да|Да|

> [!NOTE]
> Хотя не <xref:System.Windows.Controls.TextBox> поддерживает такие команды форматирования, как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctrl + B), многие основные команды поддерживаются обоими элементами управления, такими как <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> .

Функции из приведенной выше таблицы будут подробно рассматриваться далее.

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a>Создание элемента управления RichTextBox

В приведенном ниже коде показано, как создать объект <xref:System.Windows.Controls.RichTextBox> , который пользователь может редактировать с содержимым в.

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

В частности, содержимое, измененное в, <xref:System.Windows.Controls.RichTextBox> является нефиксированным содержимым. Содержимое нефиксированного формата может включать множество типов элементов, в том числе форматированный текст, изображения, списки и таблицы. См. более подробные сведения о потоковых документах в разделе [Общие сведения о потоковых документах](../advanced/flow-document-overview.md). Чтобы вместить содержимое нефиксированного формата, объект <xref:System.Windows.Controls.RichTextBox> размещается в <xref:System.Windows.Documents.FlowDocument> объекте, который, в свою очередь, содержит редактируемое содержимое. Чтобы продемонстрировать содержимое нефиксированного формата в <xref:System.Windows.Controls.RichTextBox> , в следующем коде показано, как создать объект <xref:System.Windows.Controls.RichTextBox> с абзацем и полужирным текстом.

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

На рисунке ниже показано, как будет выглядеть этот пример.

![RichTextBox с содержимым](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")

Элементы, такие как <xref:System.Windows.Documents.Paragraph> и, <xref:System.Windows.Documents.Bold> определяют, как <xref:System.Windows.Controls.RichTextBox> отображается содержимое внутри. Когда пользователь редактирует <xref:System.Windows.Controls.RichTextBox> содержимое, он изменяет содержимое нефиксированного формата. Дополнительные сведения о возможностях подвижного содержимого и способах работы с ним см. в разделе [Общие сведения о потоковых документах](../advanced/flow-document-overview.md).

> [!NOTE]
> Содержимое нефиксированного формата внутри не работает точно так же, <xref:System.Windows.Controls.RichTextBox> как и содержимое потока, содержащееся в других элементах управления. Например, отсутствуют столбцы в и, следовательно, <xref:System.Windows.Controls.RichTextBox> Автоматическое изменение размера не выполняется. Кроме того, встроенные функции, такие как поиск, режим просмотра, Навигация по страницам и масштаб, недоступны в <xref:System.Windows.Controls.RichTextBox> .

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a>Проверка орфографии в режиме реального времени

Проверку орфографии в режиме реального времени можно включить в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox> . При включенной проверке орфографии все слова с ошибками подчеркиваются красной линией (см. рисунок ниже).

![Текстовое поле с проверкой орфографии&#45;](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")

Чтобы научиться включать проверку правописания, см. раздел [Включение проверки орфографии в элементе управления редактирования текста](how-to-enable-spell-checking-in-a-text-editing-control.md).

<a name="context_menu"></a>

## <a name="context-menu"></a>Контекстное меню

По умолчанию <xref:System.Windows.Controls.TextBox> и, и <xref:System.Windows.Controls.RichTextBox> имеют контекстное меню, отображаемое, когда пользователь щелкает правой кнопкой мыши внутри элемента управления. Контекстное меню дает пользователю возможность вырезания, копирования и вставки (см. рисунок ниже).

![TextBox с контекстным меню](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")

Можно создать собственное пользовательское контекстное меню, чтобы переопределить меню по умолчанию. Дополнительные сведения см. в разделе [Расположение пользовательского контекстного меню в RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md).

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a>Команды изменения

Команды редактирования позволяют пользователям форматировать содержимое, доступное для редактирования, в <xref:System.Windows.Controls.RichTextBox> . Помимо основных команд редактирования <xref:System.Windows.Controls.RichTextBox> включает команды форматирования, которые <xref:System.Windows.Controls.TextBox> не поддерживаются. Например, при редактировании в <xref:System.Windows.Controls.RichTextBox> пользователь может нажать сочетание клавиш CTRL + B, чтобы включить форматирование текста полужирным шрифтом. <xref:System.Windows.Documents.EditingCommands>Полный список доступных команд см. в разделе. Помимо использования сочетания клавиш, можно подключать команды к другим элементам управления, таким как кнопки. В следующем примере показано, как создать простую панель инструментов, содержащую кнопки, с помощью которых пользователь может изменять форматирование текста.

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

На следующем рисунке показано, как будет выглядеть этот пример.

![RichTextBox с панелью инструментов](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a>Определение изменения содержимого

Обычно <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> событие следует использовать для обнаружения изменений текста в или, а не в том виде, в <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.UIElement.KeyDown> котором они могут ожидать. Пример см. в разделе [Определение изменения текста в TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md).

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a>Сохранение, загрузка и печать содержимого RichTextBox

В следующем примере показано, как сохранить содержимое в <xref:System.Windows.Controls.RichTextBox> файл, загрузить содержимое обратно в <xref:System.Windows.Controls.RichTextBox> и распечатать содержимое. Ниже для примера приведена разметка.

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

Ниже для примера приведен код.

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a>См. также

- [Практические руководства](richtextbox-how-to-topics.md)
- [Общие сведения о TextBox](textbox-overview.md)
