---
title: Практическое руководство. Создание настраиваемого конструктора действий
description: В этой статье описывается создание настраиваемого конструктора действий Workflow Foundation с зоной перетаскивания, в которой можно поместить произвольное действие.
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: 015efd1e482e2b531d28b9caec411c76116c9653
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419789"
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="3b9d9-103">Практическое руководство. Создание настраиваемого конструктора действий</span><span class="sxs-lookup"><span data-stu-id="3b9d9-103">How to: Create a Custom Activity Designer</span></span>

<span data-ttu-id="3b9d9-104">Пользовательские конструкторы действий обычно реализуются таким образом, что их связанные действия сочетаются с другими действиями, конструкторы которых могут сбрасываться вместе с ними в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-104">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="3b9d9-105">Для этой функции требуется, чтобы конструктор настраиваемых действий предоставил "область перетаскивания", где можно разместить произвольное действие, а также средства управления результирующей коллекцией элементов в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-105">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="3b9d9-106">В этом разделе описано создание пользовательского конструктора действий, содержащего «зону перетаскивания», а также создание пользовательского конструктора действий, предоставляющего функции редактирования, необходимые для управления коллекцией элементов конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-106">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>

<span data-ttu-id="3b9d9-107">Пользовательские конструкторы действий обычно наследуют от <xref:System.Activities.Presentation.ActivityDesigner>, который является базовым типом конструктора действий по умолчанию для любых действий без определенного конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-107">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="3b9d9-108">Этот тип обеспечивает взаимодействие с таблицей свойств во время разработки и настройку основных аспектов, например, управления цветами и значками.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-108">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>

<span data-ttu-id="3b9d9-109">Для упрощения разработки пользовательских конструкторов действий в конструкторе <xref:System.Activities.Presentation.ActivityDesigner> используют два элемента управления помощника, <xref:System.Activities.Presentation.WorkflowItemPresenter> и <xref:System.Activities.Presentation.WorkflowItemsPresenter>.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-109"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="3b9d9-110">Они обрабатывают общие функции, например перетаскивание дочерних элементов, удаление, выделение и добавление этих дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-110">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="3b9d9-111"><xref:System.Activities.Presentation.WorkflowItemPresenter>Компонент позволяет одному дочернему элементу пользовательского интерфейса внутри, предоставляя "Drop Zone", в то время как <xref:System.Activities.Presentation.WorkflowItemsPresenter> может предоставлять поддержку нескольких элементов пользовательского интерфейса, включая дополнительные функциональные возможности, такие как упорядочивание, перемещение, удаление и добавление дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-111">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>

<span data-ttu-id="3b9d9-112">Вторая часть статьи, которая требует выделения в реализации пользовательского конструктора действий, связана с тем, как визуальные изменения привязываются с помощью привязки данных WPF к экземпляру, сохраненному в памяти того, что мы редактируем в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-112">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using WPF data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="3b9d9-113">Это достигается с помощью дерева элементов модели, которое также обеспечивает уведомления об изменениях и отслеживание таких событий, как изменения состояний.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-113">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>

<span data-ttu-id="3b9d9-114">В данном подразделе описаны две процедуры.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-114">This topic outlines two procedures.</span></span>

1. <span data-ttu-id="3b9d9-115">Первая процедура описывает создание пользовательских конструкторов действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>, предоставляющим «зону перетаскивания», в которую можно помещать другие действия.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-115">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="3b9d9-116">Эта процедура основана на примере [пользовательских составных конструкторов — представление элементов рабочего процесса](./samples/custom-composite-designers-workflow-item-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-116">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>

2. <span data-ttu-id="3b9d9-117">Вторая процедура описывает создание пользовательских конструкторов действий с элементом управления помощника <xref:System.Activities.Presentation.WorkflowItemsPresenter>, предоставляющим функции, необходимые для изменения коллекции содержащихся в нем элементов.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-117">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="3b9d9-118">Эта процедура основана на примере [пользовательских составных конструкторов — представление элементов рабочего процесса](./samples/custom-composite-designers-workflow-items-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-118">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="3b9d9-119">Создание пользовательского конструктора действий с "зоной сброса" с использованием WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="3b9d9-119">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>

1. <span data-ttu-id="3b9d9-120">Запустите Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-120">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="3b9d9-121">В меню **файл** наведите указатель мыши на пункт **создать**и выберите **проект...**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-121">On the **File** menu, point to **New**, and then select **Project…**.</span></span>

     <span data-ttu-id="3b9d9-122">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-122">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="3b9d9-123">В области **Установленные шаблоны** выберите **Windows** из категории предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-123">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>

4. <span data-ttu-id="3b9d9-124">В области **шаблоны** выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-124">In the **Templates** pane, select **WPF Application**.</span></span>

5. <span data-ttu-id="3b9d9-125">В поле **имя** введите `UsingWorkflowItemPresenter` .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-125">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>

6. <span data-ttu-id="3b9d9-126">В поле **Расположение** введите каталог, в котором необходимо сохранить проект, или нажмите кнопку **Обзор** , чтобы перейти к нему.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-126">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>

7. <span data-ttu-id="3b9d9-127">В поле **решение** примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-127">In the **Solution** box, accept the default value.</span></span>

8. <span data-ttu-id="3b9d9-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-128">Click **OK**.</span></span>

9. <span data-ttu-id="3b9d9-129">Щелкните правой кнопкой мыши файл *MainWindow. XAML* в **Обозреватель решений**, выберите **Удалить** и подтвердите **ОК** в диалоговом окне **Microsoft Visual Studio** .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-129">Right-click the *MainWindows.xaml* file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialog box.</span></span>

10. <span data-ttu-id="3b9d9-130">Щелкните правой кнопкой мыши проект Усингворкфловитемпресентер в **Обозреватель решений**, выберите **Добавить**, а затем **новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="3b9d9-130">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="3b9d9-131">чтобы открыть диалоговое окно **Добавление нового элемента** и выбрать категорию **WPF** в разделе **Установленные шаблоны** слева.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-131">to bring up the **Add New Item** dialog and select the **WPF** category from the **Installed Templates** section on the left.</span></span>

11. <span data-ttu-id="3b9d9-132">Выберите шаблон **Window (WPF)** , присвойте ему имя `RehostingWFDesigner` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-132">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>

12. <span data-ttu-id="3b9d9-133">Откройте файл *рехостингвфдесигнер. XAML* и вставьте в него следующий код, чтобы определить пользовательский интерфейс для приложения:</span><span class="sxs-lookup"><span data-stu-id="3b9d9-133">Open the *RehostingWFDesigner.xaml* file and paste the following code into it to define the UI for the application:</span></span>

    ```xaml
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"
            xmlns:sys="clr-namespace:System;assembly=mscorlib"
            Title="Window1" Height="600" Width="900">
        <Window.Resources>
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>
        </Window.Resources>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="2*"/>
                <ColumnDefinition Width="7*"/>
                <ColumnDefinition Width="3*"/>
            </Grid.ColumnDefinitions>
            <Border Grid.Column="0">
                <sapt:ToolboxControl Name="Toolbox">
                    <sapt:ToolboxCategory CategoryName="Basic">
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.Sequence
                            </sapt:ToolboxItemWrapper.ToolName>
                           </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.WriteLine
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.If
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.While
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                    </sapt:ToolboxCategory>
                </sapt:ToolboxControl>
            </Border>
            <Border Grid.Column="1" Name="DesignerBorder"/>
            <Border Grid.Column="2" Name="PropertyBorder"/>
        </Grid>
    </Window>
    ```

13. <span data-ttu-id="3b9d9-134">Чтобы связать конструктор действия с типом действия, необходимо зарегистрировать конструктор действия в хранилище метаданных.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-134">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="3b9d9-135">Для этого добавьте метод `RegisterMetadata` в класс `RehostingWFDesigner`.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-135">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="3b9d9-136">В области метода `RegisterMetadata` создайте объект <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> и вызовите метод <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>, чтобы добавить к нему атрибуты.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-136">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="3b9d9-137">Вызовите метод <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>, чтобы добавить <xref:System.Activities.Presentation.Metadata.AttributeTable> в хранилище метаданных.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-137">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="3b9d9-138">Следующий код содержит логику повторного размещения для конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-138">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="3b9d9-139">Он регистрирует метаданные, помещает действие `SimpleNativeActivity` в область элементов и создает рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-139">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="3b9d9-140">Вставьте этот код в файл *RehostingWFDesigner.XAML.CS* .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-140">Put this code into the *RehostingWFDesigner.xaml.cs* file.</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Presentation.Toolbox;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespace UsingWorkflowItemPresenter
    {
        // Interaction logic for RehostingWFDesigner.xaml
        public partial class RehostingWFDesigner
        {
            public RehostingWFDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // Add custom activity to toolbox.
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. <span data-ttu-id="3b9d9-141">Щелкните правой кнопкой мыши каталог References в обозреватель решений и выберите команду **Добавить ссылку...**</span><span class="sxs-lookup"><span data-stu-id="3b9d9-141">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="3b9d9-142">для открытия диалогового окна **Добавление ссылки** .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-142">to bring up the **Add Reference** dialog.</span></span>

15. <span data-ttu-id="3b9d9-143">Перейдите на вкладку **.NET** , укажите сборку с именем **System. activitys. Core. Presentation**, выберите ее и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-143">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>

16. <span data-ttu-id="3b9d9-144">Таким же образом добавьте ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="3b9d9-144">Using the same procedure, add references to the following assemblies:</span></span>

    1. <span data-ttu-id="3b9d9-145">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="3b9d9-145">System.Data.DataSetExtensions.dll</span></span>

    2. <span data-ttu-id="3b9d9-146">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="3b9d9-146">System.Activities.Presentation.dll</span></span>

    3. <span data-ttu-id="3b9d9-147">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="3b9d9-147">System.ServiceModel.Activities.dll</span></span>

17. <span data-ttu-id="3b9d9-148">Откройте файл *app. XAML* и измените значение StartUpUri на рехостингвфдесигнер. XAML.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-148">Open the *App.xaml* file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>

18. <span data-ttu-id="3b9d9-149">Щелкните правой кнопкой мыши проект Усингворкфловитемпресентер в **Обозреватель решений**, выберите **Добавить**, а затем **новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="3b9d9-149">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="3b9d9-150">чтобы открыть диалоговое окно **Добавление нового элемента** , выберите категорию **Рабочий процесс** в разделе **Установленные шаблоны** слева.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-150">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

19. <span data-ttu-id="3b9d9-151">Выберите шаблон **конструктор действий** , присвойте ему имя `SimpleNativeDesigner` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-151">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>

20. <span data-ttu-id="3b9d9-152">Откройте файл *симпленативедесигнер. XAML* и вставьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-152">Open the *SimpleNativeDesigner.xaml* file and paste the following code into it.</span></span> <span data-ttu-id="3b9d9-153">Обратите внимание, что этот код использует <xref:System.Activities.Presentation.ActivityDesigner> в качестве корневого элемента и показывает, как привязка используется для интеграции <xref:System.Activities.Presentation.WorkflowItemPresenter> в конструктор, чтобы дочерний тип можно было отобразить в конструкторе составных действий.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-153">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b9d9-154">Схема для <xref:System.Activities.Presentation.ActivityDesigner> позволяет добавлять только один дочерний элемент в определение пользовательского конструктора действий. Однако этим элементом может быть `StackPanel`, `Grid` или другой составной элемент пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-154">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <StackPanel>
                    <TextBlock>This is the collapsed view</TextBlock>
                </StackPanel>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock>Custom Text</TextBlock>
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                            HintText="Please drop an activity here" />
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
        </Grid>
    </sap:ActivityDesigner>
    ```

21. <span data-ttu-id="3b9d9-155">Щелкните правой кнопкой мыши проект Усингворкфловитемпресентер в **Обозреватель решений**, выберите **Добавить**, а затем **новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="3b9d9-155">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="3b9d9-156">чтобы открыть диалоговое окно **Добавление нового элемента** , выберите категорию **Рабочий процесс** в разделе **Установленные шаблоны** слева.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-156">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

22. <span data-ttu-id="3b9d9-157">Выберите шаблон **действие кода** , присвойте ему имя `SimpleNativeActivity` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-157">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>

23. <span data-ttu-id="3b9d9-158">Реализуйте `SimpleNativeActivity` класс, введя следующий код в файл *SimpleNativeActivity.CS* :</span><span class="sxs-lookup"><span data-stu-id="3b9d9-158">Implement the `SimpleNativeActivity` class by entering the following code into the *SimpleNativeActivity.cs* file:</span></span>

    ```csharp
    using System.Activities;

    namespace UsingWorkflowItemPresenter
    {
        public sealed class SimpleNativeActivity : NativeActivity
        {
            // this property contains an activity that will be scheduled in the execute method
            // the WorkflowItemPresenter in the designer is bound to this to enable editing
            // of the value
            public Activity Body { get; set; }

            protected override void CacheMetadata(NativeActivityMetadata metadata)
            {
               metadata.AddChild(Body);
               base.CacheMetadata(metadata);

            }

            protected override void Execute(NativeActivityContext context)
            {
                context.ScheduleActivity(Body);
            }
        }
    }
    ```

24. <span data-ttu-id="3b9d9-159">В меню **Сборка** выберите пункт **построить решение** .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-159">Select **Build Solution** from the **Build** menu.</span></span>

25. <span data-ttu-id="3b9d9-160">Выберите **Запуск без отладки** в меню **Отладка** , чтобы открыть повторно размещенное настраиваемое окно конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-160">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="3b9d9-161">Создание пользовательского конструктора действий с использованием WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="3b9d9-161">To create a custom activity designer using WorkflowItemsPresenter</span></span>

1. <span data-ttu-id="3b9d9-162">Процедура для второго конструктора настраиваемых действий является параллельной с небольшими изменениями, первый из которых — имя второго приложения `UsingWorkflowItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-162">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="3b9d9-163">Кроме того, это приложение не определяет новое пользовательское действие.</span><span class="sxs-lookup"><span data-stu-id="3b9d9-163">Also this application does not define a new custom activity.</span></span>

2. <span data-ttu-id="3b9d9-164">Ключевые отличия содержатся в файлах *кустомпараллелдесигнер. XAML* и *RehostingWFDesigner.XAML.CS* .</span><span class="sxs-lookup"><span data-stu-id="3b9d9-164">Key differences are contained in the *CustomParallelDesigner.xaml* and *RehostingWFDesigner.xaml.cs* files.</span></span> <span data-ttu-id="3b9d9-165">Ниже приведен код из файла *кустомпараллелдесигнер. XAML* , определяющего пользовательский интерфейс:</span><span class="sxs-lookup"><span data-stu-id="3b9d9-165">Here is the code from the *CustomParallelDesigner.xaml* file that defines the UI:</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <TextBlock>This is the Collapsed View</TextBlock>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"
                                        Items="{Binding Path=ModelItem.Branches}">
                        <sap:WorkflowItemsPresenter.SpacerTemplate>
                            <DataTemplate>
                                <Ellipse Width="10" Height="10" Fill="Black"/>
                            </DataTemplate>
                        </sap:WorkflowItemsPresenter.SpacerTemplate>
                        <sap:WorkflowItemsPresenter.ItemsPanel>
                            <ItemsPanelTemplate>
                                <StackPanel Orientation="Horizontal"/>
                            </ItemsPanelTemplate>
                        </sap:WorkflowItemsPresenter.ItemsPanel>
                    </sap:WorkflowItemsPresenter>
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
        </Grid>
    </sap:ActivityDesigner>
    ```

3. <span data-ttu-id="3b9d9-166">Ниже приведен код из файла *RehostingWFDesigner.XAML.CS* , который предоставляет логику повторного размещения:</span><span class="sxs-lookup"><span data-stu-id="3b9d9-166">Here is the code from the *RehostingWFDesigner.xaml.cs* file that provides the rehosting logic:</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespaceUsingWorkflowItemsPresenter
    {
        public partial class RehostingWfDesigner : Window
        {
            public RehostingWfDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="3b9d9-167">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3b9d9-167">See also</span></span>

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [<span data-ttu-id="3b9d9-168">Рекомендации по настройке конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3b9d9-168">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
