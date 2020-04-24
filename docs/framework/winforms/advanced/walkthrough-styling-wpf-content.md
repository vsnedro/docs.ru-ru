---
title: 'Прохождение: Стиль WPF содержание'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646328"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="66cff-102">Прохождение: Стиль WPF содержание</span><span class="sxs-lookup"><span data-stu-id="66cff-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="66cff-103">В этой статье показан, как применять стиль к управлению Windows Presentation Foundation (WPF), размещенном в форме Windows.</span><span class="sxs-lookup"><span data-stu-id="66cff-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66cff-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="66cff-104">Prerequisites</span></span>

<span data-ttu-id="66cff-105">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66cff-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="66cff-106">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="66cff-106">Create the project</span></span>

<span data-ttu-id="66cff-107">Откройте Visual Studio и создайте новый проект приложения `StylingWpfContent`Windows Forms в visual Basic или Visual C ' под названием .</span><span class="sxs-lookup"><span data-stu-id="66cff-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="66cff-108">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="66cff-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="66cff-109">Создание типов управления WPF</span><span class="sxs-lookup"><span data-stu-id="66cff-109">Create the WPF control types</span></span>

<span data-ttu-id="66cff-110">После добавления в проект типа элемента управления WPF можно разместить его в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="66cff-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="66cff-111">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="66cff-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="66cff-112">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="66cff-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="66cff-113">Для получения дополнительной информации [см.](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="66cff-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="66cff-114">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="66cff-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="66cff-115">В окне **Свойств** установите <xref:System.Windows.FrameworkElement.Width%2A> значение <xref:System.Windows.FrameworkElement.Height%2A> и свойства до **200**.</span><span class="sxs-lookup"><span data-stu-id="66cff-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="66cff-116">Добавьте <xref:System.Windows.Controls.Button?displayProperty=nameWithType> элемент <xref:System.Windows.Controls.UserControl> управления в и <xref:System.Windows.Controls.ContentControl.Content%2A> установите значение свойства для **отмены.**</span><span class="sxs-lookup"><span data-stu-id="66cff-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="66cff-117">Добавьте <xref:System.Windows.Controls.Button?displayProperty=nameWithType> второй элемент <xref:System.Windows.Controls.UserControl> управления и установите значение <xref:System.Windows.Controls.ContentControl.Content%2A> свойства в **OK.**</span><span class="sxs-lookup"><span data-stu-id="66cff-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="66cff-118">Создайте проект.</span><span class="sxs-lookup"><span data-stu-id="66cff-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="66cff-119">Примените стиль к управлению WPF</span><span class="sxs-lookup"><span data-stu-id="66cff-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="66cff-120">Для изменения внешнего вида и поведения элемента управления WPF к нему можно применить различные стили.</span><span class="sxs-lookup"><span data-stu-id="66cff-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="66cff-121">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="66cff-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="66cff-122">В **Toolbox**, дважды `UserControl1` нажмите, `UserControl1` чтобы создать экземпляр на форме.</span><span class="sxs-lookup"><span data-stu-id="66cff-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="66cff-123">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="66cff-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="66cff-124">В смарт-панели `elementHost1`тегов для , нажмите **Edit Hosted Содержание** из списка выпадающих вниз.</span><span class="sxs-lookup"><span data-stu-id="66cff-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="66cff-125">`UserControl1`открывается в WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="66cff-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="66cff-126">В представлении XAML вставьте следующий код XAML после открывающего тега `<UserControl>` .</span><span class="sxs-lookup"><span data-stu-id="66cff-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="66cff-127">Этот код XAML создает градиент с контрастной градиентной границей.</span><span class="sxs-lookup"><span data-stu-id="66cff-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="66cff-128">При нажатии на элемент управления градиенты изменяются, формируя образ нажатой кнопки.</span><span class="sxs-lookup"><span data-stu-id="66cff-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="66cff-129">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="66cff-129">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. <span data-ttu-id="66cff-130">Примените стиль, `SimpleButton` определенный в предыдущем шаге, к кнопке `<Button>` Отмена, вставив следующий XAML в тег кнопки **Отмена.**</span><span class="sxs-lookup"><span data-stu-id="66cff-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="66cff-131">Ваша кнопочно-разыскная декларация будет напоминать следующее XAML:</span><span class="sxs-lookup"><span data-stu-id="66cff-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="66cff-132">Создайте проект.</span><span class="sxs-lookup"><span data-stu-id="66cff-132">Build the project.</span></span>

1. <span data-ttu-id="66cff-133">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="66cff-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="66cff-134">Новый стиль применяется для элемента управления button.</span><span class="sxs-lookup"><span data-stu-id="66cff-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="66cff-135">Из меню **Debug** выберите **Start Debugging** для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="66cff-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="66cff-136">Нажмите кнопки **OK** и **Cancel** и просмотрите различия.</span><span class="sxs-lookup"><span data-stu-id="66cff-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="66cff-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66cff-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="66cff-138">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="66cff-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="66cff-139">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="66cff-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="66cff-140">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66cff-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="66cff-141">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="66cff-141">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="66cff-142">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="66cff-142">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
