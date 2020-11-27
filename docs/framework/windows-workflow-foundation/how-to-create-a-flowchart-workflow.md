---
title: Практическое руководство. Создание рабочего процесса c блок-схемой
description: В этой статье описывается создание рабочего процесса, который использует как встроенные действия, так и пользовательские действия из предыдущей статьи.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: f8e0703591629a72e0a8f6eeb05dd9d19c8c4c91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275831"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="8337a-103">Практическое руководство. Создание рабочего процесса c блок-схемой</span><span class="sxs-lookup"><span data-stu-id="8337a-103">How to: Create a Flowchart Workflow</span></span>

<span data-ttu-id="8337a-104">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="8337a-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="8337a-105">В этом разделе описывается создание рабочего процесса, который использует как встроенные действия, такие как <xref:System.Activities.Statements.Flowchart> действие, так и пользовательские действия из предыдущего раздела [инструкции. Создание действия](how-to-create-an-activity.md) .</span><span class="sxs-lookup"><span data-stu-id="8337a-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="8337a-106">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="8337a-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8337a-107">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="8337a-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="8337a-108">Для выполнения этой статьи сначала необходимо выполнить действия [по созданию действия](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="8337a-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8337a-109">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="8337a-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="8337a-110">Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8337a-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="8337a-111">Щелкните правой кнопкой мыши **NumberGuessWorkflowActivities** в **Обозреватель решений** и выберите **добавить**, **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="8337a-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="8337a-112">В узле **установленные** **Общие элементы** выберите **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="8337a-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="8337a-113">В списке **Рабочий процесс** выберите пункт **Действие**.</span><span class="sxs-lookup"><span data-stu-id="8337a-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="8337a-114">Введите `FlowchartNumberGuessWorkflow` в поле **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="8337a-114">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="8337a-115">Перетащите действие **блок-схема** из **раздела блок** -схема **области элементов** и поместите его в метку **Перетащите сюда действие** в рабочей области конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="8337a-115">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="8337a-116">Создание переменных и аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8337a-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="8337a-117">Дважды щелкните **FlowchartNumberGuessWorkflow. XAML** в **Обозреватель решений** , чтобы отобразить рабочий процесс в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="8337a-117">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="8337a-118">Щелкните **аргументы** в левой нижней части конструктора рабочих процессов, чтобы отобразить панель **аргументы** .</span><span class="sxs-lookup"><span data-stu-id="8337a-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="8337a-119">Нажмите кнопку **Создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="8337a-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="8337a-120">Введите в `MaxNumber` поле **имя** , выберите **в** раскрывающемся списке **направление** значение **Int32** , а затем нажмите клавишу ВВОД **Argument type** , чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="8337a-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="8337a-121">Нажмите кнопку **Создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="8337a-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="8337a-122">Введите `Turns` в поле **имя** , которое находится ниже вновь добавленного `MaxNumber` аргумента, **Out** выберите из раскрывающегося списка **направление** , выберите **Int32** из раскрывающегося списка **тип аргумента** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8337a-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="8337a-123">В левом нижнем углу конструктора действий нажмите кнопку **Аргументы**, чтобы закрыть панель **Аргументы**.</span><span class="sxs-lookup"><span data-stu-id="8337a-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="8337a-124">Щелкните **переменные** в левой нижней части конструктора рабочих процессов, чтобы отобразить панель **переменные** .</span><span class="sxs-lookup"><span data-stu-id="8337a-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="8337a-125">Нажмите кнопку **Создать переменную**.</span><span class="sxs-lookup"><span data-stu-id="8337a-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="8337a-126">Если поле **создать переменную** не отображается, щелкните <xref:System.Activities.Statements.Flowchart> действие в области конструктора рабочих процессов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="8337a-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="8337a-127">Введите `Guess` в поле **имя** , выберите **Int32** в раскрывающемся списке **тип переменной** и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="8337a-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="8337a-128">Нажмите кнопку **Создать переменную**.</span><span class="sxs-lookup"><span data-stu-id="8337a-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="8337a-129">Введите `Target` в поле **имя** , выберите **Int32** в раскрывающемся списке **тип переменной** и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="8337a-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="8337a-130">В левом нижнем углу конструктора действий нажмите кнопку **Переменные**, чтобы закрыть панель **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="8337a-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="8337a-131">Добавление действий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8337a-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="8337a-132">Перетащите действие **Assign (назначение** ) из раздела **примитивы** **области элементов** и наведите его на **начальный** узел, расположенный в верхней части блок-схемы.</span><span class="sxs-lookup"><span data-stu-id="8337a-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="8337a-133">Когда действие **Assign** находится над **начальным** узлом, вокруг **начального** узла появятся три треугольника.</span><span class="sxs-lookup"><span data-stu-id="8337a-133">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="8337a-134">Удалите действие **Assign** на треугольнике, расположенном непосредственно под **начальным** узлом.</span><span class="sxs-lookup"><span data-stu-id="8337a-134">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="8337a-135">Это позволит связать два элемента вместе и назначить действие **Assign** в качестве первого действия в блок-схеме.</span><span class="sxs-lookup"><span data-stu-id="8337a-135">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8337a-136">Действия можно также указывать в качестве начального действия в рабочем процессе, вручную связав их с действием в начальном узле.</span><span class="sxs-lookup"><span data-stu-id="8337a-136">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="8337a-137">Для этого наведите указатель мыши на **начальный** узел, щелкните один из прямоугольников, отображаемых при наведении указателя мыши на **начальный** узел, и перетащите строку подключения вниз к нужному действию и поместите ее на один из отображаемых прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="8337a-137">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="8337a-138">Вы также можете назначить действие в качестве начального действия, щелкнув его правой кнопкой мыши и выбрав пункт **задать в качестве начального узла**.</span><span class="sxs-lookup"><span data-stu-id="8337a-138">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="8337a-139">Введите `Target` в поле **to** и следующее выражение в поле **введите выражение C#** или **введите выражение VB** .</span><span class="sxs-lookup"><span data-stu-id="8337a-139">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="8337a-140">Если окно **Панель элементов** не отображается, выберите пункт **Панель элементов** в меню **Вид**.</span><span class="sxs-lookup"><span data-stu-id="8337a-140">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="8337a-141">Перетащите действие **запрос** из раздела **NumberGuessWorkflowActivities** на **панели элементов**, поместите его под действием **Assign (назначение** ) из предыдущего шага и подключите действие **Prompt** к действию **Assign** .</span><span class="sxs-lookup"><span data-stu-id="8337a-141">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="8337a-142">Соединить два действия можно тремя способами.</span><span class="sxs-lookup"><span data-stu-id="8337a-142">There are three ways to connect the two activities.</span></span> <span data-ttu-id="8337a-143">Первый способ — подключить их по мере удаления действия **Prompt** в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="8337a-143">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="8337a-144">При перетаскивании действия **Prompt** в рабочий процесс наведите его на действие Assign ( **назначить** ) и поместите его на один из четырех треугольников, отображаемых, когда действие **запроса** находится над действием **Assign (назначить** ).</span><span class="sxs-lookup"><span data-stu-id="8337a-144">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="8337a-145">Второй способ — удалить действие **Prompt** в рабочем процессе в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="8337a-145">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="8337a-146">Затем наведите указатель мыши на действие **Assign (назначение** ) и перетащите один из прямоугольников, отображаемых в действие **Prompt** .</span><span class="sxs-lookup"><span data-stu-id="8337a-146">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="8337a-147">Перетащите указатель мыши, чтобы соединяющая линия из действия **назначить** подключаться к одному из прямоугольников действия **запроса** , а затем отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="8337a-147">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="8337a-148">Третий способ очень похож на первый, за исключением того, что вместо того, чтобы перетаскивать действие **Prompt** из **панели элементов**, перетащите его из своего расположения в рабочей области конструктора рабочих процессов, наведите его на действие **Assign (назначить** ) и поместите его на один из появившихся треугольников.</span><span class="sxs-lookup"><span data-stu-id="8337a-148">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="8337a-149">В **окне Свойства** действия **Prompt** введите, `"EnterGuess"` включая кавычки, в поле значение свойства **BookmarkName** .</span><span class="sxs-lookup"><span data-stu-id="8337a-149">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="8337a-150">Введите `Guess` в поле значение свойства **результата** и введите следующее выражение в поле свойства **текста** .</span><span class="sxs-lookup"><span data-stu-id="8337a-150">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="8337a-151">Если **окно Свойства** не отображается, в меню **вид** выберите пункт **окно свойств** .</span><span class="sxs-lookup"><span data-stu-id="8337a-151">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="8337a-152">Перетащите действие **Assign (назначение** ) из раздела **примитивы** **области элементов** и подключите его с помощью одного из методов, описанных в предыдущем шаге, чтобы он был ниже действия **Prompt** .</span><span class="sxs-lookup"><span data-stu-id="8337a-152">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="8337a-153">Введите `Turns` в поле **Кому** и `Turns + 1` в поле **введите выражение C#**  или **введите выражение VB** .</span><span class="sxs-lookup"><span data-stu-id="8337a-153">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="8337a-154">Перетащите **FlowDecision** из раздела **блок-схема** области **элементов** и подключите его под действием **Assign (назначение** ).</span><span class="sxs-lookup"><span data-stu-id="8337a-154">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="8337a-155">В **окне Свойства** введите следующее выражение в поле значение свойства **Condition** .</span><span class="sxs-lookup"><span data-stu-id="8337a-155">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="8337a-156">Перетащите еще одно действие **FlowDecision** из **области элементов** и поместите его под первым.</span><span class="sxs-lookup"><span data-stu-id="8337a-156">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="8337a-157">Соедините два действия, перетащив прямоугольник, помеченный как " **ложь** ", в верхнем действии **FlowDecision** на прямоугольник в верхней части второго действия **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="8337a-157">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="8337a-158">Если вы не видите метки **true** и **false** в **FlowDecision**, наведите указатель мыши на **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="8337a-158">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="8337a-159">Щелкните второе действие **FlowDecision** , чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="8337a-159">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="8337a-160">В **окне Свойства** введите следующее выражение в поле значение свойства **Condition** .</span><span class="sxs-lookup"><span data-stu-id="8337a-160">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="8337a-161">Перетащите два действия **WriteLine** из раздела **примитивы** на **панели элементов** и расположите их так, чтобы они были параллельно под двумя действиями **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="8337a-161">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="8337a-162">Соедините **истинное** действие нижнего действия **FlowDecision** с левым действием **WriteLine** и действием **false** с крайним правым действием **WriteLine** .</span><span class="sxs-lookup"><span data-stu-id="8337a-162">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="8337a-163">Щелкните левое действие **WriteLine** , чтобы выбрать его, и введите следующее выражение в поле значение свойства **текста** в **окне Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8337a-163">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="8337a-164">Соедините команду **WriteLine** с левой стороной действия **Prompt** , находящейся над ним.</span><span class="sxs-lookup"><span data-stu-id="8337a-164">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="8337a-165">Щелкните правой кнопкой мыши действие **WriteLine** , чтобы выбрать его, и введите следующее выражение в поле значение свойства **текста** в **окне Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8337a-165">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="8337a-166">Соедините действие **WriteLine** с правой стороны действия **Prompt** над ним.</span><span class="sxs-lookup"><span data-stu-id="8337a-166">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="8337a-167">В следующем примере показан завершенный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="8337a-167">The following example illustrates the completed workflow.</span></span>  
  
     ![Схема, на которой показана завершенная блок-схема Windows Workflow Foundation.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="8337a-169">Построение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8337a-169">To build the workflow</span></span>  
  
1. <span data-ttu-id="8337a-170">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="8337a-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="8337a-171">Инструкции по запуску рабочего процесса см. в следующем разделе [: запуск рабочего процесса](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8337a-171">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="8337a-172">Если вы уже выполнили [инструкции](how-to-run-a-workflow.md) по выполнению шага рабочего процесса с другим стилем рабочего процесса и хотите запустить его с помощью рабочего процесса блок-схемы из этого шага, перейдите к разделу [Создание и запуск приложения](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) , [посвященного запуску рабочего процесса](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8337a-172">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8337a-173">См. также</span><span class="sxs-lookup"><span data-stu-id="8337a-173">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="8337a-174">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="8337a-174">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="8337a-175">Разработка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8337a-175">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="8337a-176">Учебник по началу работы</span><span class="sxs-lookup"><span data-stu-id="8337a-176">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="8337a-177">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="8337a-177">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="8337a-178">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8337a-178">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
