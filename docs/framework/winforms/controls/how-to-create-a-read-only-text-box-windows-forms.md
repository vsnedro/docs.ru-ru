---
title: Практическое руководство. Создание текстового поля только для чтения
description: Узнайте, как преобразовать Редактируемое текстовое поле Windows Forms в текстовое поле Windows Forms только для чтения.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619368"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)

Можно преобразовать редактируемое Windows Forms текстовое поле в элемент управления только для чтения. Например, текстовое поле может отображать значение, которое обычно редактируется, но может не быть в данный момент из-за состояния приложения.

## <a name="to-create-a-read-only-text-box"></a>Создание текстового поля, доступного только для чтения

1. Присвойте <xref:System.Windows.Forms.TextBox> свойству элемента управления значение <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> `true` . Если свойство имеет значение `true` , пользователи по-прежнему могут прокручивать и выделять текст в текстовом поле, не разрешая изменения. Команда **копирования** работает в текстовом поле, но команды **вырезания** и **вставки** не используются.

    > [!NOTE]
    > <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>Свойство влияет только на взаимодействие с пользователем во время выполнения. Вы по-прежнему можете изменить содержимое текстового поля программно во время выполнения, изменив <xref:System.Windows.Forms.TextBox.Text%2A> свойство текстового поля.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
