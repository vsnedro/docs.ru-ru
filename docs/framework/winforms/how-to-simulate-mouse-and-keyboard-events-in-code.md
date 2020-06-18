---
title: Практическое руководство. Имитация событий мыши и клавиатуры в коде
description: Узнайте, как использовать параметры Windows Forms позволяет программно имитировать ввод с клавиатуры и мыши.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 9b453787f7fa7f5041f75e04d65557a0a3838bee
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904368"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="d5885-103">Практическое руководство. Имитация событий мыши и клавиатуры в коде</span><span class="sxs-lookup"><span data-stu-id="d5885-103">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="d5885-104">В Windows Forms предоставляется несколько возможностей для программной имитации ввода данных с помощью мыши и клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="d5885-104">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="d5885-105">В этом разделе приведен обзор этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="d5885-105">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="d5885-106">Имитация ввода с помощью мыши</span><span class="sxs-lookup"><span data-stu-id="d5885-106">Simulating Mouse Input</span></span>

<span data-ttu-id="d5885-107">Наилучшим способом имитации событий мыши является вызов метода `On`*EventName* , в результате чего происходит событие мыши, которое требуется имитировать.</span><span class="sxs-lookup"><span data-stu-id="d5885-107">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="d5885-108">Этот вариант обычно возможен только в пределах пользовательских элементов управления и форм, так как методы, которые вызывают события, защищены и недоступны вне элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="d5885-108">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="d5885-109">Например, ниже показано, как имитировать нажатие правой кнопки мыши в коде.</span><span class="sxs-lookup"><span data-stu-id="d5885-109">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="d5885-110">Чтобы нажать правую кнопку мыши программными средствами, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d5885-110">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="d5885-111">Создайте объект <xref:System.Windows.Forms.MouseEventArgs> и установите для его свойства <xref:System.Windows.Forms.MouseEventArgs.Button%2A> значение <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d5885-111">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="d5885-112">Вызовите метод <xref:System.Windows.Forms.Control.OnMouseClick%2A> с этим объектом <xref:System.Windows.Forms.MouseEventArgs> в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="d5885-112">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="d5885-113">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание элементов управления Windows Forms во время разработки](./controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="d5885-113">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="d5885-114">Существуют другие способы имитировать ввод с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="d5885-114">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="d5885-115">Например, можно программно установить свойство элемента управления, которое представляет состояние, обычно устанавливаемое с помощью ввода мыши (например, свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> элемента управления <xref:System.Windows.Forms.CheckBox> ), или напрямую вызвать делегат, связанный с событием, которое нужно имитировать.</span><span class="sxs-lookup"><span data-stu-id="d5885-115">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="d5885-116">Имитация ввода с клавиатуры</span><span class="sxs-lookup"><span data-stu-id="d5885-116">Simulating Keyboard Input</span></span>

<span data-ttu-id="d5885-117">Хотя ввод данных с клавиатуры можно имитировать с помощью подходов, описанных выше для ввода с помощью мыши, Windows Forms также предоставляет класс <xref:System.Windows.Forms.SendKeys> для отправки нажатий клавиш в активное приложение.</span><span class="sxs-lookup"><span data-stu-id="d5885-117">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="d5885-118">Если приложение предназначено для международного использования с различными клавиатурами, применение метода <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> может иметь непредсказуемые результаты и его следует избегать.</span><span class="sxs-lookup"><span data-stu-id="d5885-118">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="d5885-119">Класс <xref:System.Windows.Forms.SendKeys> был обновлен в .NET Framework 3.0, что позволило использовать его в приложениях, работающих в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="d5885-119">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="d5885-120">Усиленная система безопасности Windows Vista (известная как контроль учетных записей или UAC) не позволяет предыдущей реализации работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="d5885-120">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="d5885-121">Класс <xref:System.Windows.Forms.SendKeys> подвержен проблемам со временем, которые пришлось решать некоторым разработчикам.</span><span class="sxs-lookup"><span data-stu-id="d5885-121">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="d5885-122">Обновленная реализация по-прежнему подвержена этим проблемам, но она работает немного быстрее, поэтому существующие решения может потребоваться переработать.</span><span class="sxs-lookup"><span data-stu-id="d5885-122">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="d5885-123">Класс <xref:System.Windows.Forms.SendKeys> сначала пытается использовать предыдущую реализацию, и если это не удается, использует новую реализацию.</span><span class="sxs-lookup"><span data-stu-id="d5885-123">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="d5885-124">В результате класс <xref:System.Windows.Forms.SendKeys> может работать по-разному в разных операционных системах.</span><span class="sxs-lookup"><span data-stu-id="d5885-124">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="d5885-125">Кроме того, при использовании новой реализации класса <xref:System.Windows.Forms.SendKeys> метод <xref:System.Windows.Forms.SendKeys.SendWait%2A> не будет дожидаться обработки сообщений, если они отправляются другому процессу.</span><span class="sxs-lookup"><span data-stu-id="d5885-125">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="d5885-126">Если необходимо обеспечить согласованное поведение приложения независимо от операционной системы, можно заставить класс <xref:System.Windows.Forms.SendKeys> использовать новую реализацию, добавив указанный ниже параметр приложения в файл app.config.</span><span class="sxs-lookup"><span data-stu-id="d5885-126">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="d5885-127">Для принудительного использования классом <xref:System.Windows.Forms.SendKeys> предыдущей реализации задайте значение `"JournalHook"` .</span><span class="sxs-lookup"><span data-stu-id="d5885-127">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="d5885-128">Отправка нажатия клавиши в то же приложение</span><span class="sxs-lookup"><span data-stu-id="d5885-128">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="d5885-129">Вызовите метод <xref:System.Windows.Forms.SendKeys.Send%2A> или <xref:System.Windows.Forms.SendKeys.SendWait%2A> класса <xref:System.Windows.Forms.SendKeys> .</span><span class="sxs-lookup"><span data-stu-id="d5885-129">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="d5885-130">Указанные нажатия клавиш будут получены активным элементом управления приложения.</span><span class="sxs-lookup"><span data-stu-id="d5885-130">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="d5885-131">В примере кода ниже метод <xref:System.Windows.Forms.SendKeys.Send%2A> используется для имитации нажатия клавиши ВВОД, когда пользователь дважды щелкает по поверхности формы.</span><span class="sxs-lookup"><span data-stu-id="d5885-131">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="d5885-132">В этом примере используется форма <xref:System.Windows.Forms.Form> с одним элементом управления <xref:System.Windows.Forms.Button> , имеющим индекс перехода по клавише TAB, равный 0.</span><span class="sxs-lookup"><span data-stu-id="d5885-132">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="d5885-133">Отправка нажатия клавиши в другое приложение</span><span class="sxs-lookup"><span data-stu-id="d5885-133">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="d5885-134">Активируйте окно приложения, которое будет получать нажатия клавиш, а затем вызовите метод <xref:System.Windows.Forms.SendKeys.Send%2A> или <xref:System.Windows.Forms.SendKeys.SendWait%2A> .</span><span class="sxs-lookup"><span data-stu-id="d5885-134">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="d5885-135">Из-за отсутствия управляемого метода активации другого приложения необходимо использовать собственные методы Windows для принудительной установки фокуса на другие приложения.</span><span class="sxs-lookup"><span data-stu-id="d5885-135">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="d5885-136">В примере кода ниже с помощью вызова неуправляемого кода вызываются методы `FindWindow` и `SetForegroundWindow` для активации окна приложения "Калькулятор", а затем вызывается метод <xref:System.Windows.Forms.SendKeys.SendWait%2A> для проведения ряда вычислений в этом приложении.</span><span class="sxs-lookup"><span data-stu-id="d5885-136">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d5885-137">Параметры вызова `FindWindow` для определения положения Калькулятора зависят от версии Windows.</span><span class="sxs-lookup"><span data-stu-id="d5885-137">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="d5885-138">Следующий код находит приложение Calculator в Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d5885-138">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="d5885-139">В Windows Vista измените первый параметр на "SciCalc".</span><span class="sxs-lookup"><span data-stu-id="d5885-139">On Windows Vista, change the first parameter to "SciCalc".</span></span> <span data-ttu-id="d5885-140">Для определения нужных параметров можно использовать средство Spy++, входящее в состав Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d5885-140">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="d5885-141">Пример</span><span class="sxs-lookup"><span data-stu-id="d5885-141">Example</span></span>

<span data-ttu-id="d5885-142">В примере ниже полностью представлено приложение для предыдущих примеров кода.</span><span class="sxs-lookup"><span data-stu-id="d5885-142">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="d5885-143">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d5885-143">Compiling the Code</span></span>

<span data-ttu-id="d5885-144">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d5885-144">This example requires:</span></span>

- <span data-ttu-id="d5885-145">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d5885-145">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5885-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5885-146">See also</span></span>

- [<span data-ttu-id="d5885-147">Ввод данных пользователем в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5885-147">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
