---
title: Отладка консольного приложения .NET Core в Visual Studio
description: Узнайте, как выполнить отладку консольного приложения .NET Core в Visual Studio.
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4bd2a8a0e4b3cea55e209306dd3788552e4b61f3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005418"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="05436-103">Учебник. Отладка консольного приложения .NET Core с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05436-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="05436-104">В этом руководстве представлены средства отладки, доступные в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05436-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05436-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="05436-105">Prerequisites</span></span>

- <span data-ttu-id="05436-106">В этом руководстве используется консольное приложение, созданное в руководстве [Создание консольного приложения .NET Core в Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="05436-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="05436-107">Конфигурация отладочной сборки</span><span class="sxs-lookup"><span data-stu-id="05436-107">Debug build configuration</span></span>

<span data-ttu-id="05436-108">В Visual Studio по умолчанию используются две конфигурации сборки — *Отладка* и *Выпуск*.</span><span class="sxs-lookup"><span data-stu-id="05436-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="05436-109">Используемая конфигурация сборки отображается на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="05436-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="05436-110">На следующем изображении панели инструментов показано, что служба Visual Studio настроена для компиляции отладочной версии приложения:</span><span class="sxs-lookup"><span data-stu-id="05436-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![Панель инструментов Visual Studio с выделенным режимом отладки](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="05436-112">Сначала запустите отладочную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="05436-112">Begin by running the Debug version of the app.</span></span> <span data-ttu-id="05436-113">Конфигурация отладочной сборки отключает большинство инструментов оптимизации и предоставляет более подробные сведения о процессе сборки.</span><span class="sxs-lookup"><span data-stu-id="05436-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="05436-114">Установка точки останова</span><span class="sxs-lookup"><span data-stu-id="05436-114">Set a breakpoint</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="05436-115">Установите *точку останова* в строке, где отображается имя, дата и время, щелкнув в левом поле окна изменения кода в этой строке.</span><span class="sxs-lookup"><span data-stu-id="05436-115">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="05436-116">Кроме того, установить точку останова можно, поместив курсор в строку кода и нажав клавишу **F9** или выбрав **Отладка** > **Переключить точку останова** в строке меню.</span><span class="sxs-lookup"><span data-stu-id="05436-116">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="05436-117">Точка останова приостанавливает выполнение приложения на инструкции, *предшествующей* той строке, в которой установлена точка останова.</span><span class="sxs-lookup"><span data-stu-id="05436-117">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="05436-118">Как видно на следующем рисунке, строку с точкой останова Visual Studio обозначает подсветкой текста и красной точкой в левом поле.</span><span class="sxs-lookup"><span data-stu-id="05436-118">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![Окно приложения Visual Studio с установленной точкой останова](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="05436-120">Запустите программу в режиме отладки, нажав на панели инструментов кнопку **HelloWorld** с зеленой стрелкой.</span><span class="sxs-lookup"><span data-stu-id="05436-120">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span> <span data-ttu-id="05436-121">Доступны другие способы запуска отладки: нажмите клавишу **F5** или выберите **Отладка** > **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="05436-121">Other ways to start debugging are by pressing **F5** or by choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="05436-122">Когда программа запросит имя, введите любую строку в окне консоли и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="05436-122">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="05436-123">Выполнение программы остановится, когда будет достигнута точка останова, то есть перед выполнением метода `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="05436-123">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="05436-124">В окне **Локальные** отображаются значения переменных, которые определены в текущем выполняемом методе.</span><span class="sxs-lookup"><span data-stu-id="05436-124">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Снимок экрана с точкой останова в Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="05436-126">Окно **Интерпретация** позволяет взаимодействовать с приложением, которое вы отлаживаете.</span><span class="sxs-lookup"><span data-stu-id="05436-126">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="05436-127">Вы можете интерактивно изменить значения переменных и посмотреть, как это повлияет на работу программы.</span><span class="sxs-lookup"><span data-stu-id="05436-127">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="05436-128">Если окно **Интерпретация** не отображается, откройте его, выбрав **Отладка** > **Окна** > **Интерпретация**.</span><span class="sxs-lookup"><span data-stu-id="05436-128">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="05436-129">Введите `name = "Gracie"` в окне **Интерпретация** и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="05436-129">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="05436-130">Введите `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` в окне **Интерпретация** и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="05436-130">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="05436-131">В окне **Интерпретация** отображается значение переменной строки и свойства значения <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="05436-131">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="05436-132">Кроме того, значения переменных обновляются в окне **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="05436-132">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Окна "Локальные" и "Интерпретация" в Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="05436-134">Продолжите выполнение программы, нажав кнопку **Продолжить** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="05436-134">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="05436-135">Или выберите **Отладка** > **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="05436-135">Another way to continue is by choosing **Debug** > **Continue**.</span></span>

   <span data-ttu-id="05436-136">Значения, отображаемые в окне консоли, соответствуют изменениям, произведенным в окне **Интерпретация**.</span><span class="sxs-lookup"><span data-stu-id="05436-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![Окно консоли с указанными значениями](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="05436-138">Нажмите любую клавишу, чтобы выйти из приложения и остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="05436-138">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="05436-139">Установка условной точки останова</span><span class="sxs-lookup"><span data-stu-id="05436-139">Set a conditional breakpoint</span></span>

<span data-ttu-id="05436-140">Программа отображает строку, которую вводит пользователь.</span><span class="sxs-lookup"><span data-stu-id="05436-140">The program displays the string that the user enters.</span></span> <span data-ttu-id="05436-141">Что произойдет, если пользователь ничего не введет?</span><span class="sxs-lookup"><span data-stu-id="05436-141">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="05436-142">Это можно проверить с помощью одной из полезных функций отладки, называемой *условной точкой останова*. Условная точка останова прерывает выполнение программы, если соблюдены одно или несколько условий.</span><span class="sxs-lookup"><span data-stu-id="05436-142">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="05436-143">Чтобы проверить поведение программы в случае, когда пользователь не вводит текст, задайте условную точку останова следующим образом.</span><span class="sxs-lookup"><span data-stu-id="05436-143">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

1. <span data-ttu-id="05436-144">Щелкните правой кнопкой мыши красную точку, обозначающую точку останова.</span><span class="sxs-lookup"><span data-stu-id="05436-144">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="05436-145">В контекстном меню выберите **Условия**. Откроется диалоговое окно **Параметры точки останова**.</span><span class="sxs-lookup"><span data-stu-id="05436-145">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="05436-146">Установите флажок **Условия**, если он еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="05436-146">Select the box for **Conditions** if it's not already selected.</span></span>

   ![Редактор с панелью параметров точки останова (C#)](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="05436-148">Для **условного выражения** введите следующий код в поле, где приведен пример кода, который проверяет, имеет ли `x` значение 5.</span><span class="sxs-lookup"><span data-stu-id="05436-148">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="05436-149">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="05436-149">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="05436-150">При каждом достижении точки останова отладчик вызывает метод `String.IsNullOrEmpty(name)` и останавливается на этой строке только в том случае, если вызов метода возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="05436-150">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="05436-151">Вместо условного выражения можно указать *количество обращений* (в этом случае выполнение программы будет прерываться до тех пор, пока не будет достигнуто заданное количество обращений) или *условие фильтра* (в этом случае выполнение программы будет прерываться на основе таких атрибутов, как идентификатор потока, имя процесса и имя потока).</span><span class="sxs-lookup"><span data-stu-id="05436-151">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="05436-152">Выберите **Закрыть**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="05436-152">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="05436-153">Запустите отладку программы, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="05436-153">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="05436-154">Когда в окне консоли появится предложение ввести имя, просто нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="05436-154">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="05436-155">Так как указанное вами условие соблюдается (`name` имеет значение `null` или <xref:System.String.Empty?displayProperty=nameWithType>), выполнение программы будет остановлено при достижении точки останова, то есть перед выполнением метода `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="05436-155">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="05436-156">Выберите окно **Локальные**, в котором отображаются значения локальных переменных для текущего выполняемого метода.</span><span class="sxs-lookup"><span data-stu-id="05436-156">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="05436-157">В нашем примере этим методом является `Main`.</span><span class="sxs-lookup"><span data-stu-id="05436-157">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="05436-158">Обратите внимание, что переменная `name` имеет значение `""` или <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05436-158">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="05436-159">Убедитесь в том, что переменная содержит пустую строку, введя следующую инструкцию в окне **Интерпретация** и нажав клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="05436-159">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="05436-160">Результат равен `true`.</span><span class="sxs-lookup"><span data-stu-id="05436-160">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="05436-161">Вопросительный знак указывает окну интерпретации на необходимость [вычислить выражение](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="05436-161">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![Значение true в окне интерпретации после выполнения инструкции (C#)](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="05436-163">Нажмите кнопку **Продолжить** на панели инструментов, чтобы возобновить выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="05436-163">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="05436-164">Нажмите любую клавишу, чтобы закрыть окно консоли и остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="05436-164">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="05436-165">Очистите точку останова. Для этого щелкните красную точку в левом поле окна с кодом.</span><span class="sxs-lookup"><span data-stu-id="05436-165">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="05436-166">Или выберите **Отладка > Переключить точку останова** при выбранной строке кода.</span><span class="sxs-lookup"><span data-stu-id="05436-166">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="05436-167">Пошаговое выполнение программы</span><span class="sxs-lookup"><span data-stu-id="05436-167">Step through a program</span></span>

<span data-ttu-id="05436-168">Visual Studio позволяет выполнять программу пошагово, отслеживая результат ее выполнения.</span><span class="sxs-lookup"><span data-stu-id="05436-168">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="05436-169">Для этого обычно задают точку останова и запускают программу в небольшой части ее кода.</span><span class="sxs-lookup"><span data-stu-id="05436-169">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="05436-170">Так как программа невелика, можно выполнить ее пошагово.</span><span class="sxs-lookup"><span data-stu-id="05436-170">Since your program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="05436-171">Выберите **Отладка** > **Шаг с заходом**.</span><span class="sxs-lookup"><span data-stu-id="05436-171">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="05436-172">Или выполните отладку по одному оператору, нажимая клавишу **F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-172">Another way to debug one statement at a time is by pressing **F11**.</span></span>

   <span data-ttu-id="05436-173">Следующая выполняемая строка будет выделена, и рядом с ней появится стрелка.</span><span class="sxs-lookup"><span data-stu-id="05436-173">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="05436-174">C#</span><span class="sxs-lookup"><span data-stu-id="05436-174">C#</span></span>

   ![Метод выполнения по шагам в Visual Studio (C#)](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="05436-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05436-176">Visual Basic</span></span>

   ![Метод выполнения по шагам в Visual Studio (Visual Basic)](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="05436-178">На этом этапе в окне **Локальные** показано, что массив `args` пуст, а `name` и `date` имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05436-178">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="05436-179">Кроме того, Visual Studio открыла пустое окно консоли.</span><span class="sxs-lookup"><span data-stu-id="05436-179">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="05436-180">Нажмите клавишу **F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-180">Press **F11**.</span></span> <span data-ttu-id="05436-181">Будет выделена следующая выполняемая строка.</span><span class="sxs-lookup"><span data-stu-id="05436-181">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="05436-182">Окно **Локальные** не изменяется, и окно консоли остается пустым.</span><span class="sxs-lookup"><span data-stu-id="05436-182">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="05436-183">C#</span><span class="sxs-lookup"><span data-stu-id="05436-183">C#</span></span>

   ![Источник метода выполнения по шагам в Visual Studio (C#)](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="05436-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05436-185">Visual Basic</span></span>

   ![Источник метода выполнения по шагам в Visual Studio (Visual Basic)](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="05436-187">Нажмите клавишу **F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-187">Press **F11**.</span></span> <span data-ttu-id="05436-188">Visual Studio подсвечивает инструкцию, которая содержит присваивание значения переменной `name`.</span><span class="sxs-lookup"><span data-stu-id="05436-188">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="05436-189">В окне **Локальные** отображается, что `name` имеет значение `null`, а в окне консоли появилась строка What is your name? (Введите имя:).</span><span class="sxs-lookup"><span data-stu-id="05436-189">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="05436-190">Ответьте на этот запрос, введя строку в окно консоли и нажав клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="05436-190">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="05436-191">Консоль никак не отреагирует на это, и введенная строка не будет отображаться в окне консоли, но метод <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> получит введенные входные данные.</span><span class="sxs-lookup"><span data-stu-id="05436-191">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="05436-192">Нажмите клавишу **F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-192">Press **F11**.</span></span> <span data-ttu-id="05436-193">Visual Studio подсвечивает оператор, который содержит присваивание значения переменной `date` (`currentDate` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="05436-193">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="05436-194">В окне **Локальные** отображается значение, полученное в результате вызова метода <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05436-194">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05436-195">В окне консоли также отображается строка, указанная в командной строке.</span><span class="sxs-lookup"><span data-stu-id="05436-195">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="05436-196">Нажмите клавишу **F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-196">Press **F11**.</span></span> <span data-ttu-id="05436-197">В окне **Локальные** отображается значение переменной `date`, которому было присвоено свойство <xref:System.DateTime.Now?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05436-197">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="05436-198">В окне консоли изменений не произошло.</span><span class="sxs-lookup"><span data-stu-id="05436-198">The console window is unchanged.</span></span>

1. <span data-ttu-id="05436-199">Нажмите клавишу **F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-199">Press **F11**.</span></span> <span data-ttu-id="05436-200">Visual Studio вызывает метод <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05436-200">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05436-201">В окне консоли отображается форматированная строка.</span><span class="sxs-lookup"><span data-stu-id="05436-201">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="05436-202">Выберите **Отладка** > **Шаг с выходом**. Или отмените пошаговое выполнение, нажав сочетание клавиш **SHIFT**+**F11**.</span><span class="sxs-lookup"><span data-stu-id="05436-202">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing **Shift**+**F11**.</span></span>

   <span data-ttu-id="05436-203">В окне консоли отображается сообщение с предложением нажать любую клавишу для выхода.</span><span class="sxs-lookup"><span data-stu-id="05436-203">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="05436-204">Нажмите любую клавишу, чтобы закрыть окно консоли и остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="05436-204">Press any key to close the console window and stop debugging.</span></span>

## <a name="build-a-release-version"></a><span data-ttu-id="05436-205">Сборка версии в режиме выпуска</span><span class="sxs-lookup"><span data-stu-id="05436-205">Build a Release version</span></span>

<span data-ttu-id="05436-206">После тестирования отладочной версии приложения следует скомпилировать и протестировать версию в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="05436-206">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="05436-207">При сборке в режиме выпуска компилятор использует методы оптимизации, которые иногда могут негативно повлиять на поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="05436-207">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="05436-208">Например, оптимизации компилятора для повышения производительности могут привести к состоянию конкуренции в многопоточных приложениях.</span><span class="sxs-lookup"><span data-stu-id="05436-208">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="05436-209">Чтобы собрать и протестировать консольное приложение в режиме выпуска, переключите конфигурацию сборки из режима **Отладка** в режим **Выпуск** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="05436-209">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Панель инструментов Visual Studio по умолчанию с выделенным режимом отладки](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="05436-211">Если нажать клавишу **F5** или выбрать пункт **Собрать решение** в меню **Сборка**, Visual Studio скомпилирует версию приложения в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="05436-211">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="05436-212">Эту версию можно протестировать точно так же, как и отладочную.</span><span class="sxs-lookup"><span data-stu-id="05436-212">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="05436-213">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="05436-213">Next steps</span></span>

<span data-ttu-id="05436-214">В этом руководстве вы использовали средства отладки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05436-214">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="05436-215">В следующем руководстве вы опубликуете развертываемую версию приложения.</span><span class="sxs-lookup"><span data-stu-id="05436-215">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05436-216">Публикация консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05436-216">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
