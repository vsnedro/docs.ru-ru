---
title: Создание шаблона в WPF — рабочий стол .NET
description: Узнайте, как создать шаблон элемента управления и ссылаться на него в Windows Presentation Foundation и .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432542"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="7c5fe-103">Создание шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="7c5fe-103">Create a template for a control</span></span>

<span data-ttu-id="7c5fe-104">В Windows Presentation Foundation (WPF) можно настраивать визуальную структуру и функциональные возможности существующего элемента управления с помощью своего собственного шаблона многократного использования.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="7c5fe-105">Шаблоны можно применять глобально ко всему приложению, отдельным окнам и страницам или непосредственно к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="7c5fe-106">Большинство сценариев, в которых требуется создать новый элемент управления, можно реализовать, создав вместо этого новый шаблон для существующего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="7c5fe-107">В этой статье будет показано, как создать новый шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="7c5fe-108">Когда следует создавать ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7c5fe-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="7c5fe-109">Элементы управления имеют много свойств, таких, например, как <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="7c5fe-110">Эти свойства управляют различными аспектами внешнего вида элемента управления, но с помощью них можно внести не так много изменений.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="7c5fe-111">Например, для элемента управления <xref:System.Windows.Controls.CheckBox> можно задать синий цвет фона с помощью свойства <xref:System.Windows.Controls.Control.Foreground%2A> и курсив с помощью свойства <xref:System.Windows.Controls.Control.FontStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="7c5fe-112">Если вы хотите внести такие изменения внешнего вида элемента управления, которые не предусмотрены его свойствами, можно создать шаблон <xref:System.Windows.Controls.ControlTemplate>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="7c5fe-113">В большинстве пользовательских интерфейсов кнопка обычно выглядит как прямоугольник с текстом.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="7c5fe-114">Если вы хотите создать круглую кнопку, можно создать новый элемент управления, который наследует от кнопки или воссоздает функциональность кнопки.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="7c5fe-115">И вдобавок этот новый пользовательский элемент управления будет иметь круглую форму.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="7c5fe-116">Вы можете не создавать новые элементы управления, а просто настроить визуальный макет существующего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="7c5fe-117">Например, для круглой кнопки можно создать шаблон <xref:System.Windows.Controls.ControlTemplate> с желаемым визуальным макетом.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="7c5fe-118">С другой стороны, если вам нужен элемент управления с новыми функциями, другими свойствами и новыми параметрами, лучше создать новый <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c5fe-119">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7c5fe-119">Prerequisites</span></span>

<span data-ttu-id="7c5fe-120">Создайте новое приложение WPF и в окне *MainWindow.xaml* (или другом окне по вашему выбору) установите следующие свойства элемента **\<Window>** .</span><span class="sxs-lookup"><span data-stu-id="7c5fe-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="7c5fe-121">В качестве содержимого элемента **\<Window>** задайте следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="7c5fe-122">В итоге файл *MainWindow.xaml* должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="7c5fe-123">Если запустить приложение, оно будет выглядеть так.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-123">If you run the application, it looks like the following:</span></span>

![Окно WPF с двумя кнопками без стиля](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="7c5fe-125">Создание шаблона ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7c5fe-125">Create a ControlTemplate</span></span>

<span data-ttu-id="7c5fe-126">Чаще всего <xref:System.Windows.Controls.ControlTemplate> объявляется как ресурс в разделе `Resources` файла XAML.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="7c5fe-127">Так как шаблоны являются ресурсами, для них действуют те же правила определения области, что и для всех других ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="7c5fe-128">Проще говоря, то, где вы объявляете шаблон, влияет на то, где этот шаблон может быть применен.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="7c5fe-129">Например, если вы объявите шаблон в корневом элементе XAML-файла определения приложения, этот шаблон можно будет использовать в любом месте вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="7c5fe-130">Если вы определяете шаблон в окне, его смогут использовать только элементы управления из этого окна.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="7c5fe-131">Для начала добавьте элемент `Window.Resources` в свой файл *MainWindow.xaml*:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="7c5fe-132">Создайте новый шаблон **\<ControlTemplate>** со следующими заданными свойствами:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="7c5fe-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="7c5fe-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="7c5fe-134">Этот шаблон элемента управления будет простым:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-134">This control template will be simple:</span></span>

- <span data-ttu-id="7c5fe-135">корневой элемент этого элемента управления, <xref:System.Windows.Controls.Grid>;</span><span class="sxs-lookup"><span data-stu-id="7c5fe-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="7c5fe-136"><xref:System.Windows.Shapes.Ellipse>, чтобы кнопка отображалась круглой;</span><span class="sxs-lookup"><span data-stu-id="7c5fe-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="7c5fe-137"><xref:System.Windows.Controls.ContentPresenter> для вывода указанного пользователем содержимого кнопки.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="7c5fe-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="7c5fe-138">TemplateBinding</span></span>

<span data-ttu-id="7c5fe-139">Создавая новый шаблон <xref:System.Windows.Controls.ControlTemplate>, вы можете захотеть использовать общие свойства для изменения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="7c5fe-140">Расширение разметки [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) привязывает свойство элемента из шаблона <xref:System.Windows.Controls.ControlTemplate> к общему свойству, которое задается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="7c5fe-141">При использовании расширения [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) свойства элемента управления могут действовать в качестве параметров шаблона.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="7c5fe-142">Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="7c5fe-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="7c5fe-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="7c5fe-143">Ellipse</span></span>

<span data-ttu-id="7c5fe-144">Обратите внимание, что свойства **:::no-loc text="Fill":::** и **:::no-loc text="Stroke":::** элемента **\<Ellipse>** привязаны к свойствам <xref:System.Windows.Controls.Control.Foreground> и <xref:System.Windows.Controls.Control.Background> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="7c5fe-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="7c5fe-145">ContentPresenter</span></span>

<span data-ttu-id="7c5fe-146">Элемент [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) также добавляется в шаблон.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="7c5fe-147">Так как этот шаблон предназначен для кнопки, необходимо учитывать, что эта кнопка наследует от <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="7c5fe-148">Кнопка представляет содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-148">The button presents the content of the element.</span></span> <span data-ttu-id="7c5fe-149">Можно задать что-либо внутри кнопки, например обычный текст или даже другой элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="7c5fe-150">Оба следующих варианта — правильные кнопки:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="7c5fe-151">В обоих приведенных выше примерах текст и флажок задаются как свойство [Button.Content](xref:System.Windows.Controls.ContentControl.Content).</span><span class="sxs-lookup"><span data-stu-id="7c5fe-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="7c5fe-152">Все, что задано в качестве содержимого, может быть представлено через **\<ContentPresenter >** , что и делает шаблон.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="7c5fe-153">Если <xref:System.Windows.Controls.ControlTemplate> применяется к типу <xref:System.Windows.Controls.ContentControl>, такому как `Button`, выполняется поиск <xref:System.Windows.Controls.ContentPresenter> в дереве элементов.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="7c5fe-154">Если `ContentPresenter` обнаруживается, шаблон автоматически привязывает свойство <xref:System.Windows.Controls.ContentControl.Content> элемента управления к элементу `ContentPresenter`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="7c5fe-155">Использовать шаблон</span><span class="sxs-lookup"><span data-stu-id="7c5fe-155">Use the template</span></span>

<span data-ttu-id="7c5fe-156">Найдите кнопки, которые были объявлены в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="7c5fe-157">Задайте в свойстве <xref:System.Windows.Controls.Control.Template> второй кнопки ресурс `roundbutton`:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="7c5fe-158">Если теперь вы запустите проект и посмотрите на результат, то фон кнопки будет иметь овальную форму.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![Окно WPF с одной овальной кнопкой](media/create-apply-template/styled-button.png)

<span data-ttu-id="7c5fe-160">Вы, конечно, заметили, что кнопка не круглая, а вытянутая.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="7c5fe-161">Это стиль работы элемента **\<Ellipse>**  — он всегда растягивается, чтобы заполнить доступное пространство.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="7c5fe-162">Сделайте кнопку круглой, задав в свойствах **:::no-loc text="width":::** и **:::no-loc text="height":::** одно и то же значение:</span><span class="sxs-lookup"><span data-stu-id="7c5fe-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Окно WPF с одной круглой кнопкой](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="7c5fe-164">Добавление триггера</span><span class="sxs-lookup"><span data-stu-id="7c5fe-164">Add a Trigger</span></span>

<span data-ttu-id="7c5fe-165">Хотя кнопка с примененным шаблоном выглядит иначе, она ведет себя так же, как и любая другая кнопка.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="7c5fe-166">При нажатии кнопки срабатывает событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="7c5fe-167">Однако, как вы могли заметить, при наведении указателя мыши на кнопку визуально ничего не меняется.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="7c5fe-168">Все визуальные взаимодействия определяются шаблоном.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="7c5fe-169">В системах динамических событий и свойств, предоставляемых WPF, можно отслеживать значение конкретного свойства, а затем при необходимости изменять стиль шаблона.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="7c5fe-170">В данном примере вы будете отслеживать свойство <xref:System.Windows.UIElement.IsMouseOver> кнопки.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="7c5fe-171">Задайте новый цвет для элемента **\<Ellipse>** , который должен отображаться, когда указатель мыши наводится на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="7c5fe-172">Триггер такого типа называется *PropertyTrigger*.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="7c5fe-173">Чтобы это работало, необходимо добавить в **\<Ellipse>** имя, на которое можно ссылаться.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="7c5fe-174">Задайте имя **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="7c5fe-175">Затем добавьте новый <xref:System.Windows.Trigger> в коллекцию [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers).</span><span class="sxs-lookup"><span data-stu-id="7c5fe-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="7c5fe-176">Этот триггер будет отслеживать, когда событие `IsMouseOver` принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="7c5fe-177">Затем добавьте в **\<Trigger>** метод **\<Setter>** , который изменяет цвет в свойстве **Fill** элемента **\<Ellipse>** на новый цвет.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="7c5fe-178">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-178">Run the project.</span></span> <span data-ttu-id="7c5fe-179">Обратите внимание, что при наведении мыши на кнопку цвет **\<Ellipse>** изменяется.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![При наведении мыши на кнопку WPF цвет заливки изменяется](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="7c5fe-181">Использование VisualState</span><span class="sxs-lookup"><span data-stu-id="7c5fe-181">Use a VisualState</span></span>

<span data-ttu-id="7c5fe-182">Визуальные состояния определяются и активируются элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="7c5fe-183">Например, при наведении указателя мыши на элемент управления активируется состояние `CommonStates.MouseOver`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="7c5fe-184">Изменения свойств можно анимировать на основе текущего состояния элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="7c5fe-185">В предыдущем разделе с помощью **\<PropertyTrigger>** фон кнопки изменялся на `AliceBlue`, когда свойство `IsMouseOver` получало значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="7c5fe-186">Теперь вместо этого создайте визуальное состояние, которое анимирует изменение этого цвета, обеспечивая плавный переход.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="7c5fe-187">Дополнительные сведения об элементе *VisualStates* см. в разделе [Стили и шаблоны в WPF](../fundamentals/styles-templates-overview.md#visual-states).</span><span class="sxs-lookup"><span data-stu-id="7c5fe-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="7c5fe-188">Чтобы преобразовать **\<PropertyTrigger>** в анимированное визуальное состояние, сначала удалите элемент **\<ControlTemplate.Triggers>** из вашего шаблона.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="7c5fe-189">Затем в разделе **\<Grid>** шаблона элемента управления добавьте элемент **\<VisualStateManager.VisualStateGroups>** с **\<VisualStateGroup>** для `CommonStates`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="7c5fe-190">Определите два состояния — `Normal` и `MouseOver`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="7c5fe-191">Все анимации, определенные в **\<VisualState >** , применяются при активации соответствующего состояния.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="7c5fe-192">Создайте анимации для каждого состояния.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-192">Create animations for each state.</span></span> <span data-ttu-id="7c5fe-193">Анимации помещаются в элемент **\<Storyboard>** .</span><span class="sxs-lookup"><span data-stu-id="7c5fe-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="7c5fe-194">Дополнительные сведения о раскадровках см. в разделе [Общие сведения о раскадровках](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7c5fe-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="7c5fe-195">Норм.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-195">Normal</span></span>

  <span data-ttu-id="7c5fe-196">Это состояние анимирует заливку эллипса, восстанавливающую цвет `Background` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="7c5fe-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7c5fe-197">MouseOver</span></span>

  <span data-ttu-id="7c5fe-198">Это состояние анимирует изменение цвета `Background` эллипса на новый цвет: `Yellow`.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="7c5fe-199">Теперь **\<ControlTemplate>** должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="7c5fe-200">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-200">Run the project.</span></span> <span data-ttu-id="7c5fe-201">Обратите внимание, что при наведении мыши на кнопку изменение цвета **\<Ellipse>** анимируется.</span><span class="sxs-lookup"><span data-stu-id="7c5fe-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![При наведении мыши на кнопку WPF цвет заливки изменяется](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="7c5fe-203">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7c5fe-203">Next steps</span></span>

- [<span data-ttu-id="7c5fe-204">Создание стиля элемента управления в WPF</span><span class="sxs-lookup"><span data-stu-id="7c5fe-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="7c5fe-205">Стили и шаблоны в WPF</span><span class="sxs-lookup"><span data-stu-id="7c5fe-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7c5fe-206">Обзор ресурсов XAML</span><span class="sxs-lookup"><span data-stu-id="7c5fe-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
