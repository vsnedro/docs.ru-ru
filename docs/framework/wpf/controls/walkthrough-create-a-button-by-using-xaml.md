---
title: Пошаговое руководство. Создание кнопки с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646467"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="e24d3-102">Пошаговое руководство. Создание кнопки с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="e24d3-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="e24d3-103">Цель этого пошагового представления состоит в том, чтобы узнать, как создать анимированную кнопку для использования в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="e24d3-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="e24d3-104">В этом пошаговом пошаговом использовании стилей и шаблона используется индивидуальный ресурс кнопок, который позволяет повторно использовать код и отделить логику кнопки от объявления кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="e24d3-105">Это пошаговое [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]походе написано полностью в .</span><span class="sxs-lookup"><span data-stu-id="e24d3-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e24d3-106">Это пошаговое руководство проведет вас через шаги для создания [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] приложения, введя или копируя и вставляя в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e24d3-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="e24d3-107">Если вы предпочитаете научиться использовать конструктор для создания одного и того же приложения, [см.](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)</span><span class="sxs-lookup"><span data-stu-id="e24d3-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="e24d3-108">На следующем рисунке показаны готовые кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="e24d3-109">![Пользовательские кнопки, созданные с помощью XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="e24d3-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="e24d3-110">Создание базовых кнопок</span><span class="sxs-lookup"><span data-stu-id="e24d3-110">Create Basic Buttons</span></span>

<span data-ttu-id="e24d3-111">Начнем с создания нового проекта и добавления нескольких кнопок в окно.</span><span class="sxs-lookup"><span data-stu-id="e24d3-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="e24d3-112">Создать новый проект WPF и добавить кнопки в окно</span><span class="sxs-lookup"><span data-stu-id="e24d3-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="e24d3-113">Запустите среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e24d3-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="e24d3-114">**Создание нового проекта WPF:** В меню **файла,** укажите на **новый**, а затем нажмите **проекта**.</span><span class="sxs-lookup"><span data-stu-id="e24d3-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="e24d3-115">Найдите шаблон **приложения Windows (WPF)** и назовите проект "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="e24d3-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="e24d3-116">Это создаст скелет для приложения.</span><span class="sxs-lookup"><span data-stu-id="e24d3-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="e24d3-117">**Добавьте основные кнопки по умолчанию:** Все файлы, необходимые для этого пошагового покрешение, предоставляются шаблоном.</span><span class="sxs-lookup"><span data-stu-id="e24d3-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="e24d3-118">Откройте файл Window1.xaml, дважды нажав на него в Solution Explorer.</span><span class="sxs-lookup"><span data-stu-id="e24d3-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="e24d3-119">По умолчанию в <xref:System.Windows.Controls.Grid> Window1.xaml есть элемент.</span><span class="sxs-lookup"><span data-stu-id="e24d3-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="e24d3-120">Удалите <xref:System.Windows.Controls.Grid> элемент и добавьте [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] несколько кнопок на страницу, введя или скопив и вставив следующий выделенный код в Window1.xaml:</span><span class="sxs-lookup"><span data-stu-id="e24d3-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="e24d3-121">Нажмите F5 для запуска приложения; вы должны увидеть набор кнопок, который выглядит как следующая цифра.</span><span class="sxs-lookup"><span data-stu-id="e24d3-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="e24d3-122">![Три основные кнопки](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="e24d3-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="e24d3-123">Теперь, когда вы создали основные кнопки, вы закончили работать в файле Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="e24d3-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="e24d3-124">Остальная часть пошагового промотина фокусируется на файле app.xaml, определяя стили и шаблон для кнопок.</span><span class="sxs-lookup"><span data-stu-id="e24d3-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="e24d3-125">Набор основных свойств</span><span class="sxs-lookup"><span data-stu-id="e24d3-125">Set Basic Properties</span></span>

<span data-ttu-id="e24d3-126">Далее давайте установить некоторые свойства на этих кнопках для управления появлением и макетом кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="e24d3-127">Вместо того, чтобы устанавливать свойства на кнопках по отдельности, вы будете использовать ресурсы для определения свойств кнопок для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="e24d3-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="e24d3-128">Ресурсы приложений концептуально аналогичны внешним Каскадным стилям листов (CSS) для веб-страниц; однако, ресурсы гораздо более мощные, чем Каскадные листы стиля (CSS), как вы увидите к концу этого пошагового листа.</span><span class="sxs-lookup"><span data-stu-id="e24d3-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="e24d3-129">Чтобы узнать больше о ресурсах, [см.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)</span><span class="sxs-lookup"><span data-stu-id="e24d3-129">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="e24d3-130">Использовать стили для установки основных свойств на кнопках</span><span class="sxs-lookup"><span data-stu-id="e24d3-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="e24d3-131">**Определите блок Application.Resources:** Откройте app.xaml и добавьте следующую выделенную разметку, если она еще не существует:</span><span class="sxs-lookup"><span data-stu-id="e24d3-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="e24d3-132">Область ресурсов определяется по тому, где вы определяете ресурс.</span><span class="sxs-lookup"><span data-stu-id="e24d3-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="e24d3-133">Определение ресурсов `Application.Resources` в файле app.xaml позволяет использовать ресурс из любой точки приложения.</span><span class="sxs-lookup"><span data-stu-id="e24d3-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="e24d3-134">Подробнее об определении объема ресурсов [можно](../../../desktop-wpf/fundamentals/xaml-resources-define.md)узнать на см.</span><span class="sxs-lookup"><span data-stu-id="e24d3-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="e24d3-135">**Создайте стиль и определите основные значения свойства с его помощью:** Добавьте следующую разметку в `Application.Resources` блок.</span><span class="sxs-lookup"><span data-stu-id="e24d3-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="e24d3-136">Эта разметка <xref:System.Windows.Style> создает, что применяется ко всем <xref:System.Windows.FrameworkElement.Width%2A> кнопкам в приложении, <xref:System.Windows.FrameworkElement.Margin%2A> установив кнопки до 90 и до 10:</span><span class="sxs-lookup"><span data-stu-id="e24d3-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="e24d3-137">Свойство <xref:System.Windows.Style.TargetType%2A> указывает, что стиль применяется ко всем <xref:System.Windows.Controls.Button>объектам типа.</span><span class="sxs-lookup"><span data-stu-id="e24d3-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="e24d3-138">Каждый <xref:System.Windows.Setter> устанавливает различное <xref:System.Windows.Style>значение свойства для .</span><span class="sxs-lookup"><span data-stu-id="e24d3-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="e24d3-139">Поэтому на данный момент каждая кнопка в приложении имеет ширину 90 и маржу 10.</span><span class="sxs-lookup"><span data-stu-id="e24d3-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="e24d3-140">Если вы нажмете F5 для запуска приложения, вы увидите следующее окно.</span><span class="sxs-lookup"><span data-stu-id="e24d3-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="e24d3-141">![Кнопки с шириной равной 90 и границей 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="e24d3-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="e24d3-142">Существует гораздо больше, вы можете сделать со стилями, в том числе различные способы точной настройки объектов, указывая сложные значения свойств, и даже с помощью стилей в качестве ввода для других стилей.</span><span class="sxs-lookup"><span data-stu-id="e24d3-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="e24d3-143">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e24d3-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="e24d3-144">**Установите значение свойства стиля ресурсу:** Ресурсы позволяют использовать простой способ повторного использования общеоизвестных объектов и значений.</span><span class="sxs-lookup"><span data-stu-id="e24d3-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="e24d3-145">Особенно полезно определить сложные значения, используя ресурсы, чтобы сделать ваш код более модульным.</span><span class="sxs-lookup"><span data-stu-id="e24d3-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="e24d3-146">Добавьте следующую выделенную разметку в app.xaml.</span><span class="sxs-lookup"><span data-stu-id="e24d3-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="e24d3-147">Непосредственно под `Application.Resources` блоком, вы создали ресурс под названием "GrayBlueGradientBrush".</span><span class="sxs-lookup"><span data-stu-id="e24d3-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="e24d3-148">Этот ресурс определяет горизонтальный градиент.</span><span class="sxs-lookup"><span data-stu-id="e24d3-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="e24d3-149">Этот ресурс может быть использован в качестве свойства значение из любой точки <xref:System.Windows.Controls.Control.Background%2A> приложения, в том числе внутри кнопки стиль сеттер для свойства.</span><span class="sxs-lookup"><span data-stu-id="e24d3-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="e24d3-150">Теперь все кнопки <xref:System.Windows.Controls.Control.Background%2A> имеют значение свойства этого градиента.</span><span class="sxs-lookup"><span data-stu-id="e24d3-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="e24d3-151">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="e24d3-151">Press F5 to run the application.</span></span> <span data-ttu-id="e24d3-152">Он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e24d3-152">It should look like the following.</span></span>

     <span data-ttu-id="e24d3-153">![Кнопки с фоновым градиентом](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="e24d3-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="e24d3-154">Создайте шаблон, определяющий внешний вид кнопки</span><span class="sxs-lookup"><span data-stu-id="e24d3-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="e24d3-155">В этом разделе вы создаете шаблон, который настраивает внешний вид (презентацию) кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="e24d3-156">Презентация кнопки состоит из нескольких объектов, включая прямоугольники и другие компоненты, чтобы придать кнопке уникальный вид.</span><span class="sxs-lookup"><span data-stu-id="e24d3-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="e24d3-157">До сих пор контроль за тем, как выглядят кнопки в приложении, ограничивался изменением свойств кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="e24d3-158">Что делать, если вы хотите внести более радикальные изменения в внешний вид кнопки?</span><span class="sxs-lookup"><span data-stu-id="e24d3-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="e24d3-159">Шаблоны позволяют осуществлять мощный контроль над презентацией объекта.</span><span class="sxs-lookup"><span data-stu-id="e24d3-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="e24d3-160">Поскольку шаблоны могут использоваться в стилях, можно применить шаблон ко всем объектам, к которым применяется стиль (в этом пошаговом шаге кнопка).</span><span class="sxs-lookup"><span data-stu-id="e24d3-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="e24d3-161">Использовать шаблон для определения вида кнопки</span><span class="sxs-lookup"><span data-stu-id="e24d3-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="e24d3-162">**Настройка шаблона:** Поскольку <xref:System.Windows.Controls.Button> элементы <xref:System.Windows.Controls.Control.Template%2A> управления, такие как свойство, можно определить значение свойства шаблона так же, как и другие значения свойств, которые мы установили в <xref:System.Windows.Style> использовании <xref:System.Windows.Setter>.</span><span class="sxs-lookup"><span data-stu-id="e24d3-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="e24d3-163">Добавьте следующую выделенную разметку в стиль кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="e24d3-164">**Презентация кнопки Alter:** На этом этапе необходимо определить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e24d3-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="e24d3-165">Добавьте следующую выделенную разметку.</span><span class="sxs-lookup"><span data-stu-id="e24d3-165">Add the following highlighted markup.</span></span> <span data-ttu-id="e24d3-166">Эта разметка определяет <xref:System.Windows.Shapes.Rectangle> два элемента с закруглеными краями, а затем <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="e24d3-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="e24d3-167">Используется <xref:System.Windows.Controls.DockPanel> для размещения <xref:System.Windows.Controls.ContentPresenter> кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="e24d3-168">Содержимое <xref:System.Windows.Controls.ContentPresenter> кнопки отображается.</span><span class="sxs-lookup"><span data-stu-id="e24d3-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="e24d3-169">В этом пошаговом шаге, содержание текста ("Кнопка 1", "Кнопка 2", "Кнопка 3").</span><span class="sxs-lookup"><span data-stu-id="e24d3-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="e24d3-170">Все компоненты шаблона (прямоугольники <xref:System.Windows.Controls.DockPanel>и) выложены <xref:System.Windows.Controls.Grid>внутри .</span><span class="sxs-lookup"><span data-stu-id="e24d3-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="e24d3-171">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="e24d3-171">Press F5 to run the application.</span></span> <span data-ttu-id="e24d3-172">Он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e24d3-172">It should look like the following.</span></span>

     ![Окно с 3 кнопками](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="e24d3-174">**Добавьте стеклоэффект в шаблон:** Далее вы добавите стакан.</span><span class="sxs-lookup"><span data-stu-id="e24d3-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="e24d3-175">Сначала вы создаете некоторые ресурсы, которые создают эффект градиента стекла.</span><span class="sxs-lookup"><span data-stu-id="e24d3-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="e24d3-176">Добавьте эти ресурсы `Application.Resources` градиента в любом месте блока:</span><span class="sxs-lookup"><span data-stu-id="e24d3-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="e24d3-177">Эти ресурсы используются в <xref:System.Windows.Shapes.Shape.Fill%2A> качестве прямоугольника, <xref:System.Windows.Controls.Grid> который мы вставляем в шаблон кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="e24d3-178">Добавьте в шаблон следующую выделенную разметку.</span><span class="sxs-lookup"><span data-stu-id="e24d3-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="e24d3-179">Обратите внимание, что <xref:System.Windows.UIElement.Opacity%2A> прямоугольник `x:Name` с свойством "glassCube" составляет 0, поэтому при запуске образца, вы не видите стеклянный прямоугольник накладывается на вершине.</span><span class="sxs-lookup"><span data-stu-id="e24d3-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="e24d3-180">Это происходит потому, что мы позже добавим триггеры в шаблон, когда пользователь взаимодействует с кнопкой.</span><span class="sxs-lookup"><span data-stu-id="e24d3-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="e24d3-181">Тем не менее, вы можете увидеть, <xref:System.Windows.UIElement.Opacity%2A> как сейчас выглядит кнопка, изменив значение на 1 и запустив приложение.</span><span class="sxs-lookup"><span data-stu-id="e24d3-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="e24d3-182">См. следующий рисунок.</span><span class="sxs-lookup"><span data-stu-id="e24d3-182">See the following figure.</span></span> <span data-ttu-id="e24d3-183">Прежде чем перейти к следующему шагу, измените <xref:System.Windows.UIElement.Opacity%2A> обратно на 0.</span><span class="sxs-lookup"><span data-stu-id="e24d3-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="e24d3-184">![Пользовательские кнопки, созданные с помощью XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="e24d3-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="e24d3-185">Создание интерактивности кнопки</span><span class="sxs-lookup"><span data-stu-id="e24d3-185">Create Button Interactivity</span></span>

<span data-ttu-id="e24d3-186">В этом разделе вы создадите триггеры свойств и триггеры событий для изменения значений свойств и запуска анимации в ответ на действия пользователя, такие как перемещение указателя мыши по кнопке и нажатие кнопки.</span><span class="sxs-lookup"><span data-stu-id="e24d3-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="e24d3-187">Простой способ добавить интерактивность (мышь-за, мышь-оставить, нажмите, и так далее) заключается в определении триггеров в шаблоне или стиле.</span><span class="sxs-lookup"><span data-stu-id="e24d3-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="e24d3-188">Для создания <xref:System.Windows.Trigger>, вы определяете свойство "условие", такие как: Значение свойства кнопки <xref:System.Windows.UIElement.IsMouseOver%2A> `true`равна.</span><span class="sxs-lookup"><span data-stu-id="e24d3-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="e24d3-189">Затем вы определяете сеттеры (действия), которые происходят, когда условие триггера верно.</span><span class="sxs-lookup"><span data-stu-id="e24d3-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="e24d3-190">Для создания интерактивности кнопок</span><span class="sxs-lookup"><span data-stu-id="e24d3-190">To create button interactivity</span></span>

1. <span data-ttu-id="e24d3-191">**Добавить триггеры шаблонов:** Добавьте выделенную разметку в шаблон.</span><span class="sxs-lookup"><span data-stu-id="e24d3-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="e24d3-192">**Добавить триггеры свойств:** Добавьте выделенную разметку в `ControlTemplate.Triggers` блок:</span><span class="sxs-lookup"><span data-stu-id="e24d3-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="e24d3-193">Нажмите F5, чтобы запустить приложение и увидеть эффект, как вы запустите указатель мыши над кнопками.</span><span class="sxs-lookup"><span data-stu-id="e24d3-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="e24d3-194">**Добавить триггер фокусировки:** Далее мы добавим несколько аналогичных сеттеров для обработки случая, когда кнопка имеет фокус (например, после того, как пользователь нажмет его).</span><span class="sxs-lookup"><span data-stu-id="e24d3-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="e24d3-195">Нажмите F5, чтобы запустить приложение и нажмите на одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="e24d3-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="e24d3-196">Обратите внимание, что кнопка остается выделенной после нажатия на нее, потому что она по-прежнему имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e24d3-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="e24d3-197">Если вы нажмете другую кнопку, новая кнопка получает фокус, в то время как последняя теряет ее.</span><span class="sxs-lookup"><span data-stu-id="e24d3-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="e24d3-198">**Добавить анимации для** <xref:System.Windows.UIElement.MouseEnter> **и** <xref:System.Windows.UIElement.MouseLeave> **:** Далее мы добавляем некоторые анимации на триггеры.  </span><span class="sxs-lookup"><span data-stu-id="e24d3-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="e24d3-199">Добавьте следующую разметку `ControlTemplate.Triggers` в любом месте внутри блока.</span><span class="sxs-lookup"><span data-stu-id="e24d3-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="e24d3-200">Стеклянный прямоугольник сжимается, когда указатель мыши перемещается по кнопке и возвращается к нормальному размеру, когда указатель уходит.</span><span class="sxs-lookup"><span data-stu-id="e24d3-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="e24d3-201">Есть две анимации, которые срабатывают, когда<xref:System.Windows.UIElement.MouseEnter> указатель переходит кнопку (событие поднято).</span><span class="sxs-lookup"><span data-stu-id="e24d3-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="e24d3-202">Эти анимации сокращают стеклянный прямоугольник вдоль оси X и Y.</span><span class="sxs-lookup"><span data-stu-id="e24d3-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="e24d3-203">Обратите внимание на <xref:System.Windows.Media.Animation.DoubleAnimation> свойства <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>на элементы - и .</span><span class="sxs-lookup"><span data-stu-id="e24d3-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="e24d3-204">Указывается, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> что анимация происходит более половины <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> секунды, и указывает, что стекло сжимается на 10%.</span><span class="sxs-lookup"><span data-stu-id="e24d3-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="e24d3-205">Второй триггер события<xref:System.Windows.UIElement.MouseLeave>() просто останавливает первый.</span><span class="sxs-lookup"><span data-stu-id="e24d3-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="e24d3-206">При остановке <xref:System.Windows.Media.Animation.Storyboard>все анимированные свойства возвращаются к значениям по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e24d3-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="e24d3-207">Поэтому, когда пользователь перемещает указатель с кнопки, кнопка возвращается к тому, как это было до указателя мыши переехал над кнопкой.</span><span class="sxs-lookup"><span data-stu-id="e24d3-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="e24d3-208">Для получения дополнительной информации об анимации, [см.](../graphics-multimedia/animation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e24d3-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="e24d3-209">**Добавьте анимацию при нажатии кнопки:** Последним шагом является добавление триггера, когда пользователь нажимает на кнопку.</span><span class="sxs-lookup"><span data-stu-id="e24d3-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="e24d3-210">Добавьте следующую разметку `ControlTemplate.Triggers` в любом месте блока:</span><span class="sxs-lookup"><span data-stu-id="e24d3-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="e24d3-211">Нажмите F5, чтобы запустить приложение, и нажмите одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="e24d3-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="e24d3-212">При нажатии кнопки стеклянный прямоугольник вращается вокруг.</span><span class="sxs-lookup"><span data-stu-id="e24d3-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="e24d3-213">Сводка</span><span class="sxs-lookup"><span data-stu-id="e24d3-213">Summary</span></span>
 <span data-ttu-id="e24d3-214">В этом пошаговом шаге вы выполнили следующие упражнения:</span><span class="sxs-lookup"><span data-stu-id="e24d3-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="e24d3-215">Целевой <xref:System.Windows.Style> тип объекта ().<xref:System.Windows.Controls.Button></span><span class="sxs-lookup"><span data-stu-id="e24d3-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="e24d3-216">Управляемые основные свойства кнопок <xref:System.Windows.Style>во всем приложении с помощью .</span><span class="sxs-lookup"><span data-stu-id="e24d3-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="e24d3-217">Созданные ресурсы, такие как градиенты для использования значений <xref:System.Windows.Style> свойств сеттеров.</span><span class="sxs-lookup"><span data-stu-id="e24d3-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="e24d3-218">Настроил внешний вид кнопок во всем приложении, применяя шаблон к кнопкам.</span><span class="sxs-lookup"><span data-stu-id="e24d3-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="e24d3-219">Индивидуальное поведение для кнопок в ответ <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>на <xref:System.Windows.Controls.Primitives.ButtonBase.Click>действия пользователя (например, и), которые включали эффекты анимации.</span><span class="sxs-lookup"><span data-stu-id="e24d3-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="e24d3-220">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e24d3-220">See also</span></span>

- [<span data-ttu-id="e24d3-221">Создание кнопки с помощью Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="e24d3-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="e24d3-222">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e24d3-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e24d3-223">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="e24d3-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="e24d3-224">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="e24d3-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="e24d3-225">Общие сведения об эффектах для точечных рисунков</span><span class="sxs-lookup"><span data-stu-id="e24d3-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
