---
title: Создание действия в среде выполнения с динамическим действием
description: DynamicActivity — конкретный запечатанный класс с открытым конструктором. Используйте класс для сборки функциональности действий во время выполнения с помощью модели DOM действия.
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 17ee14be7df4801018c7afd2e91f1fb07c34e8e1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421544"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="6ebc6-104">Создание действия в среде выполнения с динамическим действием</span><span class="sxs-lookup"><span data-stu-id="6ebc6-104">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="6ebc6-105"><xref:System.Activities.DynamicActivity> представляет собой конкретный запечатанный класс с открытым конструктором.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-105"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="6ebc6-106"><xref:System.Activities.DynamicActivity> может использоваться для объединения функций действий во время выполнения с помощью действия DOM.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-106"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="6ebc6-107">Возможности DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="6ebc6-107">DynamicActivity Features</span></span>  
 <span data-ttu-id="6ebc6-108"><xref:System.Activities.DynamicActivity> имеет доступ к свойствам, аргументам и переменным выполнения, но не имеет доступа к службам среды выполнения, таким как дочерние действия планирования и отслеживание.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-108"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="6ebc6-109">Значения свойств верхнего уровня можно задавать при помощи объектов рабочих процессов <xref:System.Activities.Argument>.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-109">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="6ebc6-110">В императивном коде эти аргументы создаются при помощи свойств среды CLR в новом типе.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-110">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="6ebc6-111">На языке XAML такие аргументы объявляются при помощи тегов `x:Class` и `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-111">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="6ebc6-112">Действия, построенные при помощи интерфейса <xref:System.Activities.DynamicActivity> в конструкторе, использующем <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-112">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="6ebc6-113">Действия, созданные в конструкторе, можно загружать динамически с помощью <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, как показано в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-113">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="6ebc6-114">Создание действия во время выполнения при помощи императивного кода</span><span class="sxs-lookup"><span data-stu-id="6ebc6-114">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="6ebc6-115">Опенвисуал Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-115">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="6ebc6-116">Выберите **файл**, **создать**, **проект**.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-116">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="6ebc6-117">Выберите **Рабочий процесс 4,0** в разделе **Visual C#** в окне **типы проектов** и выберите узел **v2010** .</span><span class="sxs-lookup"><span data-stu-id="6ebc6-117">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6ebc6-118">Выберите в окне **шаблоны** **консольное приложение последовательного рабочего процесса** .</span><span class="sxs-lookup"><span data-stu-id="6ebc6-118">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="6ebc6-119">Задайте имя для нового проекта DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-119">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="6ebc6-120">Щелкните правой кнопкой мыши Workflow1. XAML в проекте Хеллоактивити и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-120">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="6ebc6-121">Откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-121">Open Program.cs.</span></span> <span data-ttu-id="6ebc6-122">Добавьте следующую директиву в начало файла.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-122">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="6ebc6-123">Замените содержимое метода `Main` следующим кодом, который создаст действие <xref:System.Activities.Statements.Sequence>, содержащее отдельное действие <xref:System.Activities.Statements.WriteLine>, и назначит его свойству <xref:System.Activities.DynamicActivity.Implementation%2A> нового динамического действия.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-123">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. <span data-ttu-id="6ebc6-124">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-124">Execute the application.</span></span> <span data-ttu-id="6ebc6-125">Окно консоли с текстом "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6ebc6-125">A console window with the text "Hello World!"</span></span> <span data-ttu-id="6ebc6-126">Отображает.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-126">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="6ebc6-127">Создание действия во время выполнения при помощи языка XAML</span><span class="sxs-lookup"><span data-stu-id="6ebc6-127">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="6ebc6-128">Откройте Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-128">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="6ebc6-129">Выберите **файл**, **создать**, **проект**.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-129">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="6ebc6-130">Выберите **Рабочий процесс 4,0** в разделе **Visual C#** в окне **типы проектов** и выберите узел **v2010** .</span><span class="sxs-lookup"><span data-stu-id="6ebc6-130">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6ebc6-131">Выберите **консольное приложение рабочего процесса** в окне **шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="6ebc6-131">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="6ebc6-132">Задайте имя для нового проекта DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-132">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="6ebc6-133">Откройте файл Workflow1.xaml в проекте HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-133">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="6ebc6-134">Щелкните параметр **arguments (аргументы** ) в нижней части конструктора.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-134">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="6ebc6-135">Создайте новый аргумент `In`, вызываемый методом `TextToWrite` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-135">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="6ebc6-136">Перетащите действие **WriteLine** из раздела **примитивы** области элементов на поверхность конструктора.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-136">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="6ebc6-137">Присвойте значение `TextToWrite` свойству **Text** действия.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-137">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="6ebc6-138">Откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-138">Open Program.cs.</span></span> <span data-ttu-id="6ebc6-139">Добавьте следующую директиву в начало файла.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-139">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="6ebc6-140">Замените содержимое метода `Main` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-140">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="6ebc6-141">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-141">Execute the application.</span></span> <span data-ttu-id="6ebc6-142">Окно консоли с текстом "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6ebc6-142">A console window with the text "Hello World!"</span></span> <span data-ttu-id="6ebc6-143">Появится .</span><span class="sxs-lookup"><span data-stu-id="6ebc6-143">appears.</span></span>  
  
8. <span data-ttu-id="6ebc6-144">Щелкните правой кнопкой мыши файл Workflow1. XAML в **Обозреватель решений** и выберите команду **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-144">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="6ebc6-145">Следует отметить, что класс действия создается при помощи `x:Class`, а свойство - при помощи `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-145">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ebc6-146">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="6ebc6-146">See also</span></span>

- [<span data-ttu-id="6ebc6-147">Разработка рабочих процессов, действий и выражений с помощью императивного кода</span><span class="sxs-lookup"><span data-stu-id="6ebc6-147">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
