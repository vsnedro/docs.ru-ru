---
title: Отладка консольного приложения .NET с помощью Visual Studio
description: Узнайте, как выполнить отладку консольного приложения .NET с помощью Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 8a914dc6cf069c011ea5b077ada514bf8cec331d
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916200"
---
# <a name="tutorial-debug-a-net-console-application-using-visual-studio"></a><span data-ttu-id="aa979-103">Учебник. Отладка консольного приложения .NET с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa979-103">Tutorial: Debug a .NET console application using Visual Studio</span></span>

<span data-ttu-id="aa979-104">В этом руководстве представлены средства отладки, доступные в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa979-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa979-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="aa979-105">Prerequisites</span></span>

- <span data-ttu-id="aa979-106">В этом руководстве используется консольное приложение, созданное в руководстве [Создание консольного приложения .NET в Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="aa979-106">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="aa979-107">Использование конфигурации отладочной сборки</span><span class="sxs-lookup"><span data-stu-id="aa979-107">Use Debug build configuration</span></span>

<span data-ttu-id="aa979-108">В Visual Studio используются две встроенные конфигурации сборки — *Отладка* и *Выпуск*.</span><span class="sxs-lookup"><span data-stu-id="aa979-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="aa979-109">Вы воспользуетесь отладочной конфигурацией сборки для отладки и конфигурацией для выпуска для окончательного выпуска программы.</span><span class="sxs-lookup"><span data-stu-id="aa979-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="aa979-110">В отладочной конфигурации программы компилируется с полной символической отладочной информацией и без оптимизации.</span><span class="sxs-lookup"><span data-stu-id="aa979-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="aa979-111">Оптимизация усложняет отладку, поскольку усложняется связь между исходным кодом и сгенерированными инструкциями.</span><span class="sxs-lookup"><span data-stu-id="aa979-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="aa979-112">Конфигурация для выпуска полностью оптимизирована и не содержит символической отладочной информации.</span><span class="sxs-lookup"><span data-stu-id="aa979-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="aa979-113">По умолчанию Visual Studio использует отладочную конфигурацию сборки, поэтому ее не нужно изменять перед отладкой.</span><span class="sxs-lookup"><span data-stu-id="aa979-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="aa979-114">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa979-114">Start Visual Studio.</span></span>

1. <span data-ttu-id="aa979-115">Откройте проект, созданный по инструкциям из статьи [Создание консольного приложения .NET в Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="aa979-115">Open the project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

   <span data-ttu-id="aa979-116">Используемая конфигурация сборки отображается на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="aa979-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="aa979-117">На следующем изображении панели инструментов показано, что служба Visual Studio настроена для компиляции отладочной версии приложения:</span><span class="sxs-lookup"><span data-stu-id="aa979-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png" alt-text="Панель инструментов Visual Studio с выделенным режимом отладки":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="aa979-119">Установка точки останова</span><span class="sxs-lookup"><span data-stu-id="aa979-119">Set a breakpoint</span></span>

<span data-ttu-id="aa979-120">*Точка останова* приостанавливает выполнение приложения на инструкции, предшествующей той строке, в которой установлена точка останова.</span><span class="sxs-lookup"><span data-stu-id="aa979-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="aa979-121">Установите *точку останова* в строке, где отображается имя, дата и время, щелкнув в левом поле окна изменения кода в этой строке.</span><span class="sxs-lookup"><span data-stu-id="aa979-121">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="aa979-122">Левое поле находится слева от номеров строк.</span><span class="sxs-lookup"><span data-stu-id="aa979-122">The left margin is to the left of the line numbers.</span></span>  <span data-ttu-id="aa979-123">Кроме того, установить точку останова можно, поместив курсор в строку кода и нажав клавишу <kbd>F9</kbd> или выбрав **Отладка** > **Переключить точку останова** в строке меню.</span><span class="sxs-lookup"><span data-stu-id="aa979-123">Other ways to set a breakpoint are by placing the cursor in the line of code and then pressing <kbd>F9</kbd> or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="aa979-124">Как видно на следующем рисунке, строку с точкой останова Visual Studio обозначает подсветкой текста и красной точкой в левом поле.</span><span class="sxs-lookup"><span data-stu-id="aa979-124">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/set-breakpoint-in-editor.png" alt-text="Окно приложения Visual Studio с установленной точкой останова":::

1. <span data-ttu-id="aa979-126">Нажмите клавишу <kbd>F5</kbd>, чтобы запустить программу в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="aa979-126">Press <kbd>F5</kbd> to run the program in Debug mode.</span></span> <span data-ttu-id="aa979-127">Еще один способ запуска отладки — выбрать в меню параметры **Отладка** > **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="aa979-127">Another way to start debugging is by choosing **Debug** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="aa979-128">Когда программа запросит имя, введите любую строку в окне консоли и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-128">Enter a string in the console window when the program prompts for a name, and then press <kbd>Enter</kbd>.</span></span>

1. <span data-ttu-id="aa979-129">Выполнение программы остановится, когда будет достигнута точка останова, то есть перед выполнением метода `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="aa979-129">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="aa979-130">В окне **Локальные** отображаются значения переменных, которые определены в текущем выполняемом методе.</span><span class="sxs-lookup"><span data-stu-id="aa979-130">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-hit.png" alt-text="Снимок экрана с точкой останова в Visual Studio":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="aa979-132">Использование окна "Интерпретация"</span><span class="sxs-lookup"><span data-stu-id="aa979-132">Use the Immediate window</span></span>

<span data-ttu-id="aa979-133">Окно **Интерпретация** позволяет взаимодействовать с приложением, которое вы отлаживаете.</span><span class="sxs-lookup"><span data-stu-id="aa979-133">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="aa979-134">Вы можете интерактивно изменить значения переменных и посмотреть, как это повлияет на работу программы.</span><span class="sxs-lookup"><span data-stu-id="aa979-134">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="aa979-135">Если окно **Интерпретация** не отображается, откройте его, выбрав **Отладка** > **Окна** > **Интерпретация**.</span><span class="sxs-lookup"><span data-stu-id="aa979-135">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

1. <span data-ttu-id="aa979-136">Введите `name = "Gracie"` в окне **Интерпретация** и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-136">Enter `name = "Gracie"` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

1. <span data-ttu-id="aa979-137">Введите `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` в окне **Интерпретация** и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-137">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="aa979-138">В окне **Интерпретация** отображается значение переменной строки и свойства значения <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="aa979-138">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="aa979-139">Кроме того, значения переменных обновляются в окне **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="aa979-139">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/locals-immediate-window.png" alt-text="Окна &quot;Локальные&quot; и &quot;Интерпретация&quot; в Visual Studio 2019":::

1. <span data-ttu-id="aa979-141">Нажмите клавишу <kbd>F5</kbd>, чтобы продолжить выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="aa979-141">Press <kbd>F5</kbd> to continue program execution.</span></span> <span data-ttu-id="aa979-142">Или выберите **Отладка** > **Продолжить** в меню.</span><span class="sxs-lookup"><span data-stu-id="aa979-142">Another way to continue is by choosing **Debug** > **Continue** from the menu.</span></span>

   <span data-ttu-id="aa979-143">Значения, отображаемые в окне консоли, соответствуют изменениям, произведенным в окне **Интерпретация**.</span><span class="sxs-lookup"><span data-stu-id="aa979-143">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/console-window.png" alt-text="Окно консоли с указанными значениями":::

1. <span data-ttu-id="aa979-145">Нажмите любую клавишу, чтобы выйти из приложения и остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="aa979-145">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="aa979-146">Установка условной точки останова</span><span class="sxs-lookup"><span data-stu-id="aa979-146">Set a conditional breakpoint</span></span>

<span data-ttu-id="aa979-147">Программа отображает строку, которую вводит пользователь.</span><span class="sxs-lookup"><span data-stu-id="aa979-147">The program displays the string that the user enters.</span></span> <span data-ttu-id="aa979-148">Что произойдет, если пользователь ничего не введет?</span><span class="sxs-lookup"><span data-stu-id="aa979-148">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="aa979-149">Это можно проверить с помощью полезной функции отладки, которая называется *условной точкой останова*.</span><span class="sxs-lookup"><span data-stu-id="aa979-149">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="aa979-150">Щелкните правой кнопкой мыши красную точку, обозначающую точку останова.</span><span class="sxs-lookup"><span data-stu-id="aa979-150">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="aa979-151">В контекстном меню выберите **Условия**. Откроется диалоговое окно **Параметры точки останова**.</span><span class="sxs-lookup"><span data-stu-id="aa979-151">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="aa979-152">Установите флажок **Условия**, если он еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="aa979-152">Select the box for **Conditions** if it's not already selected.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-settings.png" alt-text="Редактор с панелью параметров точки останова (C#)":::

1. <span data-ttu-id="aa979-154">Для **условного выражения** введите следующий код в поле, где приведен пример кода, который проверяет, имеет ли `x` значение 5.</span><span class="sxs-lookup"><span data-stu-id="aa979-154">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="aa979-155">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="aa979-155">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="aa979-156">При каждом достижении точки останова отладчик вызывает метод `String.IsNullOrEmpty(name)` и останавливается на этой строке только в том случае, если вызов метода возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="aa979-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="aa979-157">Вместо условного выражения можно указать *количество обращений* (выполнение программы будет прервано, пока инструкция не будет выполнена указанное количество раз)</span><span class="sxs-lookup"><span data-stu-id="aa979-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="aa979-158">или *условие фильтра* (выполнение программы будет прервано на основе таких атрибутов, как идентификатор потока, имя процесса или имя потока).</span><span class="sxs-lookup"><span data-stu-id="aa979-158">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="aa979-159">Выберите **Закрыть**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="aa979-159">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="aa979-160">Запустите отладку программы, нажав клавишу <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-160">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="aa979-161">Когда в окне консоли появится предложение ввести имя, просто нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-161">In the console window, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

1. <span data-ttu-id="aa979-162">Так как указанное вами условие соблюдается (`name` имеет значение `null` или <xref:System.String.Empty?displayProperty=nameWithType>), выполнение программы будет остановлено при достижении точки останова, то есть перед выполнением метода `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="aa979-162">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="aa979-163">Выберите окно **Локальные**, в котором отображаются значения локальных переменных для текущего выполняемого метода.</span><span class="sxs-lookup"><span data-stu-id="aa979-163">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="aa979-164">В нашем примере этим методом является `Main`.</span><span class="sxs-lookup"><span data-stu-id="aa979-164">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="aa979-165">Обратите внимание, что переменная `name` имеет значение `""` или <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa979-165">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="aa979-166">Убедитесь в том, что переменная содержит пустую строку, введя следующую инструкцию в окне **Интерпретация** и нажав клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-166">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="aa979-167">Результат равен `true`.</span><span class="sxs-lookup"><span data-stu-id="aa979-167">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="aa979-168">Вопросительный знак указывает окну интерпретации на необходимость [вычислить выражение](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="aa979-168">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/immediate-window-output.png" alt-text="Значение true в окне интерпретации после выполнения инструкции (C#)":::

1. <span data-ttu-id="aa979-170">Нажмите клавишу <kbd>F5</kbd>, чтобы продолжить выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="aa979-170">Press <kbd>F5</kbd> to continue program execution.</span></span>

1. <span data-ttu-id="aa979-171">Нажмите любую клавишу, чтобы закрыть окно консоли и остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="aa979-171">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="aa979-172">Очистите точку останова. Для этого щелкните красную точку в левом поле окна с кодом.</span><span class="sxs-lookup"><span data-stu-id="aa979-172">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="aa979-173">Или нажмите клавишу <kbd>F9</kbd> либо выберите в меню пункт **Отладка > Перейти к следующей точке останова** при выбранной строке кода.</span><span class="sxs-lookup"><span data-stu-id="aa979-173">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="aa979-174">Пошаговое выполнение программы</span><span class="sxs-lookup"><span data-stu-id="aa979-174">Step through a program</span></span>

<span data-ttu-id="aa979-175">Visual Studio позволяет выполнять программу пошагово, отслеживая результат ее выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa979-175">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="aa979-176">Для этого обычно задают точку останова и запускают программу в небольшой части ее кода.</span><span class="sxs-lookup"><span data-stu-id="aa979-176">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="aa979-177">Поскольку наша программа невелика, давайте выполним ее пошагово.</span><span class="sxs-lookup"><span data-stu-id="aa979-177">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="aa979-178">Выберите **Отладка** > **Шаг с заходом**.</span><span class="sxs-lookup"><span data-stu-id="aa979-178">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="aa979-179">Или выполните отладку по одному оператору, нажимая клавишу <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-179">Another way to debug one statement at a time is by pressing <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="aa979-180">Следующая выполняемая строка будет выделена, и рядом с ней появится стрелка.</span><span class="sxs-lookup"><span data-stu-id="aa979-180">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="aa979-181">C#</span><span class="sxs-lookup"><span data-stu-id="aa979-181">C#</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-method.png" alt-text="Метод выполнения по шагам в Visual Studio (C#)":::

   <span data-ttu-id="aa979-183">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa979-183">Visual Basic</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-method.png" alt-text="Метод выполнения по шагам в Visual Studio (Visual Basic)":::

   <span data-ttu-id="aa979-185">На этом этапе в окне **Локальные** показано, что массив `args` пуст, а `name` и `date` имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa979-185">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="aa979-186">Кроме того, Visual Studio открыла пустое окно консоли.</span><span class="sxs-lookup"><span data-stu-id="aa979-186">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="aa979-187">Нажмите клавишу <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-187">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="aa979-188">Будет выделена следующая выполняемая строка.</span><span class="sxs-lookup"><span data-stu-id="aa979-188">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="aa979-189">Окно **Локальные** не изменяется, и окно консоли остается пустым.</span><span class="sxs-lookup"><span data-stu-id="aa979-189">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="aa979-190">C#</span><span class="sxs-lookup"><span data-stu-id="aa979-190">C#</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-source-method.png" alt-text="Источник метода выполнения по шагам в Visual Studio (C#)":::

   <span data-ttu-id="aa979-192">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa979-192">Visual Basic</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-source-method.png" alt-text="Источник метода выполнения по шагам в Visual Studio (Visual Basic)":::

1. <span data-ttu-id="aa979-194">Нажмите клавишу <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-194">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="aa979-195">Visual Studio подсвечивает инструкцию, которая содержит присваивание значения переменной `name`.</span><span class="sxs-lookup"><span data-stu-id="aa979-195">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="aa979-196">В окне **Локальные** отображается, что `name` имеет значение `null`, а в окне консоли появилась строка What is your name? (Введите имя:).</span><span class="sxs-lookup"><span data-stu-id="aa979-196">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="aa979-197">Ответьте на этот запрос, введя строку в окно консоли и нажав клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-197">Respond to the prompt by entering a string in the console window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="aa979-198">Консоль никак не отреагирует на это, и введенная строка не будет отображаться в окне консоли, но метод <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> получит введенные входные данные.</span><span class="sxs-lookup"><span data-stu-id="aa979-198">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="aa979-199">Нажмите клавишу <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-199">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="aa979-200">Visual Studio подсвечивает оператор, который содержит присваивание значения переменной `date` (`currentDate` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa979-200">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="aa979-201">В окне **Локальные** отображается значение, полученное в результате вызова метода <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa979-201">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aa979-202">В окне консоли также отображается строка, указанная в командной строке.</span><span class="sxs-lookup"><span data-stu-id="aa979-202">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="aa979-203">Нажмите клавишу <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-203">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="aa979-204">В окне **Локальные** отображается значение переменной `date`, которому было присвоено свойство <xref:System.DateTime.Now?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa979-204">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="aa979-205">В окне консоли изменений не произошло.</span><span class="sxs-lookup"><span data-stu-id="aa979-205">The console window is unchanged.</span></span>

1. <span data-ttu-id="aa979-206">Нажмите клавишу <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-206">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="aa979-207">Visual Studio вызывает метод <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa979-207">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aa979-208">В окне консоли отображается форматированная строка.</span><span class="sxs-lookup"><span data-stu-id="aa979-208">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="aa979-209">Выберите **Отладка** > **Шаг с выходом**. Или отмените пошаговое выполнение, нажав сочетание клавиш <kbd>SHIFT</kbd>+<kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aa979-209">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   <span data-ttu-id="aa979-210">В окне консоли отображается сообщение с предложением нажать любую клавишу для выхода.</span><span class="sxs-lookup"><span data-stu-id="aa979-210">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="aa979-211">Нажмите любую клавишу, чтобы закрыть окно консоли и остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="aa979-211">Press any key to close the console window and stop debugging.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="aa979-212">Использование конфигурации сборки для выпуска</span><span class="sxs-lookup"><span data-stu-id="aa979-212">Use Release build configuration</span></span>

<span data-ttu-id="aa979-213">После тестирования отладочной версии приложения следует скомпилировать и протестировать версию в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="aa979-213">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="aa979-214">При сборке в режиме выпуска компилятор использует методы оптимизации, которые иногда могут негативно повлиять на поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="aa979-214">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="aa979-215">Например, оптимизации компилятора для повышения производительности могут привести к состоянию конкуренции в многопоточных приложениях.</span><span class="sxs-lookup"><span data-stu-id="aa979-215">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="aa979-216">Чтобы собрать и протестировать консольное приложение в режиме выпуска, переключите конфигурацию сборки из режима **Отладка** в режим **Выпуск** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="aa979-216">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

:::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Панель инструментов Visual Studio по умолчанию с выделенным выпуском":::

<span data-ttu-id="aa979-218">Если нажать клавишу <kbd>F5</kbd> или выбрать пункт **Собрать решение** в меню **Сборка**, Visual Studio скомпилирует версию приложения в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="aa979-218">When you press <kbd>F5</kbd> or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="aa979-219">Эту версию можно протестировать точно так же, как и отладочную.</span><span class="sxs-lookup"><span data-stu-id="aa979-219">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa979-220">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="aa979-220">Next steps</span></span>

<span data-ttu-id="aa979-221">В этом руководстве вы использовали средства отладки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa979-221">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="aa979-222">В следующем руководстве вы опубликуете развертываемую версию приложения.</span><span class="sxs-lookup"><span data-stu-id="aa979-222">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="aa979-223">Публикация консольного приложения .NET с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa979-223">Publish a .NET console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
