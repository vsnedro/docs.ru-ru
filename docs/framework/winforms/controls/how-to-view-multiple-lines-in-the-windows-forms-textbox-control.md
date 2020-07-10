---
title: Просмотр нескольких строк в элементе управления TextBox
description: Узнайте, как просмотреть несколько строк в элементе управления TextBox Windows Forms, установив свойства Multiline, WordWrap и ScrollBars.
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174475"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Практическое руководство. Многострочные элементы управления TextBox в Windows Forms
По умолчанию <xref:System.Windows.Forms.TextBox> элемент управления Windows Forms отображает одну строку текста и не отображает полосы прокрутки. Если текст превышает доступное пространство, отображается только часть текста. Это поведение по умолчанию можно изменить, задав <xref:System.Windows.Forms.TextBox.Multiline%2A> <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> <xref:System.Windows.Forms.TextBox.ScrollBars%2A> для свойств, и соответствующие значения.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Отображение возврата каретки в элементе управления TextBox  
  
- Чтобы отобразить возврат каретки в многострочном коде <xref:System.Windows.Forms.TextBox> , используйте <xref:System.Environment.NewLine%2A> свойство.  
  
     Имейте в виду, что интерпретация escape-символов ( \\ ) зависит от языка. Visual Basic использует `Chr$(13) & Chr$(10)` для сочетания символов возврата каретки и перевода строки.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Просмотр нескольких строк в элементе управления TextBox  
  
1. Задайте для свойства <xref:System.Windows.Forms.TextBox.Multiline%2A> значение `true`. Если <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `true` (по умолчанию), то текст в элементе управления будет отображаться как один или несколько абзацев; в противном случае он будет отображаться в виде списка, в котором некоторые строки могут быть обрезаны по границе элемента управления.  
  
2. Присвойте свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующее значение.  
  
    |Значение|Описание|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Используйте это значение, если текст будет абзацем, который почти всегда соответствует элементу управления. Пользователь может использовать указатель мыши для перемещения внутри элемента управления, если текст слишком длинный, чтобы отобразить все одновременно.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Используйте это значение, если требуется отобразить список строк, некоторые из которых могут быть длиннее ширины <xref:System.Windows.Forms.TextBox> элемента управления.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Используйте это значение, если список может быть длиннее, чем высота элемента управления.|  
  
3. Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.  
  
    |Значение|Описание|  
    |-----------|-----------------|  
    |`false`|Текст в элементе управления не будет автоматически заключаться в оболочку, поэтому он будет прокручиваться вправо до тех пор, пока не будет достигнут разрыв строки. Используйте это значение, если выбраны <xref:System.Windows.Forms.ScrollBars.Horizontal> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.Both> выше.|  
    |`true` (по умолчанию)|Горизонтальная полоса прокрутки не будет отображаться. Используйте это значение, если вы выбрали <xref:System.Windows.Forms.ScrollBars.Vertical> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.None> выше, чтобы отобразить один или несколько абзацев.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
