---
title: Реагирование на нажатия кнопок
description: Узнайте, как реагировать на нажатия кнопок Windows Forms. Самый простой способ использования элемента управления "кнопка Windows Forms" — запуск некоторого кода при нажатии кнопки.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619732"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Практическое руководство. Обработка события нажатия кнопки в Windows Forms
Самым простым использованием <xref:System.Windows.Forms.Button> элемента управления Windows Forms является выполнение некоторого кода при нажатии кнопки.  
  
 При щелчке <xref:System.Windows.Forms.Button> элемента управления также создается ряд других событий, таких как <xref:System.Windows.Forms.Control.MouseEnter> события, <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp> . Если вы планируете присоединить обработчики событий для этих связанных событий, убедитесь, что их действия не конфликтуют. Например, если нажать кнопку, чтобы очистить сведения, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должно отображаться всплывающая подсказка с несуществующими сведениями.  
  
 Если пользователь пытается дважды щелкнуть <xref:System.Windows.Forms.Button> элемент управления, каждый щелчок будет обрабатываться отдельно, то есть элемент управления не поддерживает событие двойного щелчка.  
  
### <a name="to-respond-to-a-button-click"></a>Реагирование на нажатие кнопки  
  
- В этой кнопке `Click` <xref:System.EventHandler> напишите код для выполнения. `Button1_Click`должен быть привязан к элементу управления. Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Элемент управления Button](button-control-windows-forms.md)
