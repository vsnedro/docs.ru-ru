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
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="cd605-104">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd605-104">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="cd605-105">Самым простым использованием <xref:System.Windows.Forms.Button> элемента управления Windows Forms является выполнение некоторого кода при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="cd605-105">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="cd605-106">При щелчке <xref:System.Windows.Forms.Button> элемента управления также создается ряд других событий, таких как <xref:System.Windows.Forms.Control.MouseEnter> события, <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="cd605-106">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="cd605-107">Если вы планируете присоединить обработчики событий для этих связанных событий, убедитесь, что их действия не конфликтуют.</span><span class="sxs-lookup"><span data-stu-id="cd605-107">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="cd605-108">Например, если нажать кнопку, чтобы очистить сведения, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должно отображаться всплывающая подсказка с несуществующими сведениями.</span><span class="sxs-lookup"><span data-stu-id="cd605-108">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="cd605-109">Если пользователь пытается дважды щелкнуть <xref:System.Windows.Forms.Button> элемент управления, каждый щелчок будет обрабатываться отдельно, то есть элемент управления не поддерживает событие двойного щелчка.</span><span class="sxs-lookup"><span data-stu-id="cd605-109">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="cd605-110">Реагирование на нажатие кнопки</span><span class="sxs-lookup"><span data-stu-id="cd605-110">To respond to a button click</span></span>  
  
- <span data-ttu-id="cd605-111">В этой кнопке `Click` <xref:System.EventHandler> напишите код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="cd605-111">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="cd605-112">`Button1_Click`должен быть привязан к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="cd605-112">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="cd605-113">Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cd605-113">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd605-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cd605-114">See also</span></span>

- [<span data-ttu-id="cd605-115">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="cd605-115">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="cd605-116">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd605-116">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="cd605-117">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="cd605-117">Button Control</span></span>](button-control-windows-forms.md)
