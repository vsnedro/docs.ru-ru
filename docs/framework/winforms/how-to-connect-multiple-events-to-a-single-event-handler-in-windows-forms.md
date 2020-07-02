---
title: Как подключить несколько событий к одному обработчику событий
description: Узнайте, как подключить несколько событий к одному обработчику событий в Windows Forms с помощью представления событий окно свойств в C#.
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621890"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="1806d-103">Практическое руководство. Подключение нескольких событий к одному обработчику в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1806d-103">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="1806d-104">В структуре приложения может оказаться необходимым использовать один обработчик событий для нескольких событий или несколько событий выполняют одну и ту же процедуру.</span><span class="sxs-lookup"><span data-stu-id="1806d-104">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="1806d-105">Например, зачастую очень мощная временная заставка для того, чтобы команда меню вызывала то же самое событие, что и кнопка в форме, если они предоставляют те же функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="1806d-105">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="1806d-106">Это можно сделать с помощью представления событий окно свойств в C# или с помощью раскрывающихся `Handles` списков **имя класса** и **имя метода** в Visual Basic редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="1806d-106">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="1806d-107">Подключение нескольких событий к одному обработчику событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1806d-107">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="1806d-108">Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="1806d-108">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="1806d-109">В раскрывающемся списке **имя класса** выберите один из элементов управления, для которых требуется дескриптор обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="1806d-109">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="1806d-110">В раскрывающемся списке **имя метода** выберите одно из событий, которое должен обработать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1806d-110">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="1806d-111">Редактор кода вставляет соответствующий обработчик событий и размещает точку вставки в методе.</span><span class="sxs-lookup"><span data-stu-id="1806d-111">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="1806d-112">В приведенном ниже примере это <xref:System.Windows.Forms.Control.Click> событие для <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1806d-112">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="1806d-113">Добавьте другие события, которые вы хотите обработать в `Handles` предложении.</span><span class="sxs-lookup"><span data-stu-id="1806d-113">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="1806d-114">Добавьте соответствующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1806d-114">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="1806d-115">Подключение нескольких событий к одному обработчику событий на языке C\#</span><span class="sxs-lookup"><span data-stu-id="1806d-115">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="1806d-116">Выберите элемент управления, к которому необходимо подключить обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1806d-116">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="1806d-117">В окно свойств нажмите кнопку **события** (![кнопка события](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="1806d-117">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="1806d-118">Щелкните имя события, которое требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="1806d-118">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="1806d-119">В разделе значение рядом с именем события нажмите кнопку раскрывающегося списка, чтобы отобразить список существующих обработчиков событий, соответствующих сигнатуре метода события, которое требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="1806d-119">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="1806d-120">Выберите из списка соответствующий обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1806d-120">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="1806d-121">Код будет добавлен в форму для привязки события к существующему обработчику событий.</span><span class="sxs-lookup"><span data-stu-id="1806d-121">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1806d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1806d-122">See also</span></span>

- [<span data-ttu-id="1806d-123">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1806d-123">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="1806d-124">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="1806d-124">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
