---
title: Создание шаблона в WPF - .NET Desktop
description: Узнайте, как создать и ссылку на шаблон управления в Windows Presentation Foundation и .NET Core.
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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432542"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="9d000-103">Создание шаблона для управления</span><span class="sxs-lookup"><span data-stu-id="9d000-103">Create a template for a control</span></span>

<span data-ttu-id="9d000-104">С помощью Фонда презентации Windows (WPF) вы можете настроить визуальную структуру и поведение существующего элемента управления с помощью собственного многоразового шаблона.</span><span class="sxs-lookup"><span data-stu-id="9d000-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="9d000-105">Шаблоны могут быть применены по всему миру к вашему приложению, окнам и страницам или непосредственно к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="9d000-106">Большинство сценариев, требующих создания нового элемента управления, могут быть охвачены вместо этого созданием нового шаблона для существующего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="9d000-107">В этой статье вы исследуете создание нового <xref:System.Windows.Controls.ControlTemplate> элемента <xref:System.Windows.Controls.Button> управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="9d000-108">Когда создавать ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="9d000-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="9d000-109">Элементы управления имеют <xref:System.Windows.Controls.Border.Background%2A>множество <xref:System.Windows.Controls.Control.Foreground%2A>свойств, таких как , и <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d000-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="9d000-110">Эти свойства управляют различными аспектами внешнего вида элемента управления, но изменения, которые можно внести, установив эти свойства, ограничены.</span><span class="sxs-lookup"><span data-stu-id="9d000-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="9d000-111">Например, можно установить <xref:System.Windows.Controls.Control.Foreground%2A> свойство <xref:System.Windows.Controls.Control.FontStyle%2A> на синий <xref:System.Windows.Controls.CheckBox>и курсивна на .</span><span class="sxs-lookup"><span data-stu-id="9d000-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="9d000-112">Если вы хотите настроить внешний вид элемента управления сверх того, что может <xref:System.Windows.Controls.ControlTemplate>сделать установка других свойств на элементе управления, создается.</span><span class="sxs-lookup"><span data-stu-id="9d000-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="9d000-113">В большинстве пользовательских интерфейсов кнопка имеет тот же общий внешний вид: прямоугольник с некоторым текстом.</span><span class="sxs-lookup"><span data-stu-id="9d000-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="9d000-114">Если вы хотите создать закруглена кнопка, вы можете создать новый элемент управления, который наследует от кнопки или воссоздает функциональность кнопки.</span><span class="sxs-lookup"><span data-stu-id="9d000-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="9d000-115">Кроме того, новый пользовательский контроль обеспечит круговой визуальный эффект.</span><span class="sxs-lookup"><span data-stu-id="9d000-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="9d000-116">Вы можете избежать создания новых элементов управления, настроив визуальную компоновку существующего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="9d000-117">С закругленной кнопкой, вы создаете <xref:System.Windows.Controls.ControlTemplate> с желаемой визуальной компоновкой.</span><span class="sxs-lookup"><span data-stu-id="9d000-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="9d000-118">С другой стороны, если вам нужен элемент управления с новой функциональностью, различными свойствами и новыми настройками, вы создадите новый <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="9d000-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d000-119">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9d000-119">Prerequisites</span></span>

<span data-ttu-id="9d000-120">Создайте новое приложение WPF и в *MainWindow.xaml* (или другом окне по вашему выбору) установите следующие свойства на элементе \*\* \<window>:\*\*</span><span class="sxs-lookup"><span data-stu-id="9d000-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="9d000-121">Установите содержимое \*\* \<\*\* элемента Window>на следующее XAML:</span><span class="sxs-lookup"><span data-stu-id="9d000-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="9d000-122">В конце концов, файл *MainWindow.xaml* должен выглядеть так же, как и следующее:</span><span class="sxs-lookup"><span data-stu-id="9d000-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="9d000-123">Если вы запустите приложение, оно выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d000-123">If you run the application, it looks like the following:</span></span>

![Окно WPF с двумя нестилейными кнопками](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="9d000-125">Создание шаблона ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="9d000-125">Create a ControlTemplate</span></span>

<span data-ttu-id="9d000-126">Наиболее распространенный <xref:System.Windows.Controls.ControlTemplate> способ декларировать `Resources` является ресурсом в разделе в файле XAML.</span><span class="sxs-lookup"><span data-stu-id="9d000-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="9d000-127">Поскольку шаблоны являются ресурсами, они подчиняются тем же правилам отслеживания, которые применяются ко всем ресурсам.</span><span class="sxs-lookup"><span data-stu-id="9d000-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="9d000-128">Проще говоря, если вы объявите шаблон влияет, где шаблон может быть применен.</span><span class="sxs-lookup"><span data-stu-id="9d000-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="9d000-129">Например, если вы объявите шаблон в корневом элементе файла XAML- приложения, шаблон можно использовать в любом месте приложения.</span><span class="sxs-lookup"><span data-stu-id="9d000-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="9d000-130">Если вы определяете шаблон в окне, только элементы управления в этом окне могут использовать шаблон.</span><span class="sxs-lookup"><span data-stu-id="9d000-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="9d000-131">Для начала добавьте `Window.Resources` элемент в файл *MainWindow.xaml:*</span><span class="sxs-lookup"><span data-stu-id="9d000-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="9d000-132">Создайте новую \*\* \<>ControlTemplate\*\* со следующим набором свойств:</span><span class="sxs-lookup"><span data-stu-id="9d000-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="9d000-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="9d000-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="9d000-134">Этот шаблон управления будет прост:</span><span class="sxs-lookup"><span data-stu-id="9d000-134">This control template will be simple:</span></span>

- <span data-ttu-id="9d000-135">корневой элемент для управления,<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="9d000-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="9d000-136"><xref:System.Windows.Shapes.Ellipse> чтобы нарисовать округлые внешний вид кнопки</span><span class="sxs-lookup"><span data-stu-id="9d000-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="9d000-137">для <xref:System.Windows.Controls.ContentPresenter> отображения заданного пользователем кнопок</span><span class="sxs-lookup"><span data-stu-id="9d000-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="9d000-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="9d000-138">TemplateBinding</span></span>

<span data-ttu-id="9d000-139">При создании нового, <xref:System.Windows.Controls.ControlTemplate>вы все еще можете использовать общедоступные свойства для изменения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="9d000-140">Расширение разметки [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) связывает свойство элемента, напавающего в <xref:System.Windows.Controls.ControlTemplate> государственную собственность, определяемую контролем.</span><span class="sxs-lookup"><span data-stu-id="9d000-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="9d000-141">При использовании [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)вы позволяете свойствам элемента управления действовать в качестве параметров шаблона.</span><span class="sxs-lookup"><span data-stu-id="9d000-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="9d000-142">Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="9d000-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="9d000-143">Эллипс</span><span class="sxs-lookup"><span data-stu-id="9d000-143">Ellipse</span></span>

<span data-ttu-id="9d000-144">Обратите **:::no-loc text="Fill":::** внимание, **:::no-loc text="Stroke":::** что свойства <xref:System.Windows.Controls.Control.Foreground> \*\* \<элемента Ellipse>\*\* связаны <xref:System.Windows.Controls.Control.Background> с элементами управления и свойствами.</span><span class="sxs-lookup"><span data-stu-id="9d000-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="9d000-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="9d000-145">ContentPresenter</span></span>

<span data-ttu-id="9d000-146">В шаблон также добавляется элемент [ \<ContentPresenter>.](xref:System.Windows.Controls.ContentPresenter)</span><span class="sxs-lookup"><span data-stu-id="9d000-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="9d000-147">Поскольку этот шаблон предназначен для кнопки, примите <xref:System.Windows.Controls.ContentControl>во внимание, что кнопка наследует от .</span><span class="sxs-lookup"><span data-stu-id="9d000-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="9d000-148">Кнопка представляет содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="9d000-148">The button presents the content of the element.</span></span> <span data-ttu-id="9d000-149">Вы можете установить что-нибудь внутри кнопки, например, простой текст или даже другой элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="9d000-150">Оба из них являются действительными кнопками:</span><span class="sxs-lookup"><span data-stu-id="9d000-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="9d000-151">В обоих предыдущих примерах текст и флажок устанавливаются как свойство [Button.Content.](xref:System.Windows.Controls.ContentControl.Content)</span><span class="sxs-lookup"><span data-stu-id="9d000-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="9d000-152">Все, что устанавливается как содержание может быть представленчерез через \*\* \<ContentPresenter>\*\*, который является то, что шаблон делает.</span><span class="sxs-lookup"><span data-stu-id="9d000-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="9d000-153">Если <xref:System.Windows.Controls.ControlTemplate> применяется к <xref:System.Windows.Controls.ContentControl> типу, `Button`например, a, <xref:System.Windows.Controls.ContentPresenter> поиск в дереве элемента.</span><span class="sxs-lookup"><span data-stu-id="9d000-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="9d000-154">При `ContentPresenter` обнаружении шаблон автоматически связывает свойство <xref:System.Windows.Controls.ContentControl.Content> элемента `ContentPresenter`управления с .</span><span class="sxs-lookup"><span data-stu-id="9d000-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="9d000-155">Использовать шаблон</span><span class="sxs-lookup"><span data-stu-id="9d000-155">Use the template</span></span>

<span data-ttu-id="9d000-156">Найдите кнопки, которые были объявлены в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="9d000-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="9d000-157">Установите свойство <xref:System.Windows.Controls.Control.Template> второй кнопки на `roundbutton` ресурс:</span><span class="sxs-lookup"><span data-stu-id="9d000-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="9d000-158">Если вы запустите проект и посмотрите на результат, вы увидите, что кнопка имеет закругленный фон.</span><span class="sxs-lookup"><span data-stu-id="9d000-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![Окно WPF с одной овальной кнопкой шаблона](media/create-apply-template/styled-button.png)

<span data-ttu-id="9d000-160">Возможно, вы заметили, что кнопка не круг, но перекос.</span><span class="sxs-lookup"><span data-stu-id="9d000-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="9d000-161">Из-за того, как работает элемент \*\* \<Ellipse>,\*\* он всегда расширяется, чтобы заполнить доступное пространство.</span><span class="sxs-lookup"><span data-stu-id="9d000-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="9d000-162">Сделайте круг равномерным, **:::no-loc text="width":::** изменив кнопку и **:::no-loc text="height":::** свойства на одно и то же значение:</span><span class="sxs-lookup"><span data-stu-id="9d000-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Окно WPF с одной круговой кнопкой шаблона](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="9d000-164">Добавить триггер</span><span class="sxs-lookup"><span data-stu-id="9d000-164">Add a Trigger</span></span>

<span data-ttu-id="9d000-165">Несмотря на то, что кнопка с прикладным шаблоном выглядит по-другому, она ведет себя так же, как и любая другая кнопка.</span><span class="sxs-lookup"><span data-stu-id="9d000-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="9d000-166">Если вы нажмете на кнопку, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие срастанет.</span><span class="sxs-lookup"><span data-stu-id="9d000-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="9d000-167">Тем не менее, вы могли заметить, что при перемещении мыши по кнопке визуальные эффекты кнопки не меняются.</span><span class="sxs-lookup"><span data-stu-id="9d000-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="9d000-168">Все эти визуальные взаимодействия определяются шаблоном.</span><span class="sxs-lookup"><span data-stu-id="9d000-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="9d000-169">С помощью динамических систем событий и свойств, которые предоставляет WPF, вы можете посмотреть определенное свойство для значения, а затем рестайлинг шаблона, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="9d000-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="9d000-170">В этом примере вы будете наблюдать <xref:System.Windows.UIElement.IsMouseOver> за свойством кнопки.</span><span class="sxs-lookup"><span data-stu-id="9d000-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="9d000-171">Когда мышь над управлением, стиль \*\* \<Ellipse>\*\* с новым цветом.</span><span class="sxs-lookup"><span data-stu-id="9d000-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="9d000-172">Этот тип триггера известен как *PropertyTrigger.*</span><span class="sxs-lookup"><span data-stu-id="9d000-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="9d000-173">Для того, чтобы это сработало, необходимо добавить имя в \*\* \<>,\*\* на которую вы можете ссылаться.</span><span class="sxs-lookup"><span data-stu-id="9d000-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="9d000-174">Дайте ему название **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="9d000-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="9d000-175">Затем добавьте <xref:System.Windows.Trigger> новую коллекцию [ControlTemplate.Triggers.](xref:System.Windows.Controls.ControlTemplate.Triggers)</span><span class="sxs-lookup"><span data-stu-id="9d000-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="9d000-176">Триггер будет наблюдать `IsMouseOver` за событием для значения. `true`</span><span class="sxs-lookup"><span data-stu-id="9d000-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="9d000-177">Затем добавьте \*\* \<>сеттера\*\* в \*\* \<>триггера,\*\* которая изменяет свойство **заполнения** \*\* \<>На\*\* новый цвет.</span><span class="sxs-lookup"><span data-stu-id="9d000-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="9d000-178">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="9d000-178">Run the project.</span></span> <span data-ttu-id="9d000-179">Обратите внимание, что при перемещении мыши по кнопке цвет \*\* \<Ellipse>\*\* изменяется.</span><span class="sxs-lookup"><span data-stu-id="9d000-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![мышь перемещается по кнопке WPF, чтобы изменить цвет заполнения](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="9d000-181">Использование VisualState</span><span class="sxs-lookup"><span data-stu-id="9d000-181">Use a VisualState</span></span>

<span data-ttu-id="9d000-182">Визуальные состояния определяются и запускаются элементом управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="9d000-183">Например, когда мышь перемещается поверх элемента управления, `CommonStates.MouseOver` срабатывает состояние.</span><span class="sxs-lookup"><span data-stu-id="9d000-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="9d000-184">Вы можете анимировать изменения свойств в зависимости от текущего состояния элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="9d000-185">В предыдущем разделе \*\* \<>PropertyTrigger\*\* использовался для изменения переднего `AliceBlue` плана `IsMouseOver` кнопки `true`на время, когда свойство было .</span><span class="sxs-lookup"><span data-stu-id="9d000-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="9d000-186">Вместо этого создайте визуальное состояние, которое оживляет изменение этого цвета, обеспечивая плавный переход.</span><span class="sxs-lookup"><span data-stu-id="9d000-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="9d000-187">Для получения дополнительной информации о *VisualStates*, [см.](../fundamentals/styles-templates-overview.md#visual-states)</span><span class="sxs-lookup"><span data-stu-id="9d000-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="9d000-188">Чтобы преобразовать \*\* \<>PropertyTrigger\*\* в анимированное визуальное состояние, во-первых, удалите \*\* \<элемент ControlTemplate.Triggers>\*\* элемент из шаблона.</span><span class="sxs-lookup"><span data-stu-id="9d000-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="9d000-189">Далее, в \*\* \<сетке>\*\* корень шаблона управления, добавить \*\* \<VisualStateManager.VisualStateGroups>\*\* элемент с \*\* \<VisualStateGroup>\*\* для `CommonStates`.</span><span class="sxs-lookup"><span data-stu-id="9d000-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="9d000-190">Определите два `Normal` `MouseOver`состояния, и .</span><span class="sxs-lookup"><span data-stu-id="9d000-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="9d000-191">Любые анимации, \*\* \<\*\* определенные в>VisualState, применяются при срабатывании этого состояния.</span><span class="sxs-lookup"><span data-stu-id="9d000-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="9d000-192">Создавайте анимации для каждого состояния.</span><span class="sxs-lookup"><span data-stu-id="9d000-192">Create animations for each state.</span></span> <span data-ttu-id="9d000-193">Анимации помещаются внутри \*\* \<раскадровки>\*\* элементом.</span><span class="sxs-lookup"><span data-stu-id="9d000-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="9d000-194">Для получения дополнительной информации о раскадровки, см [Storyboards Обзор](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9d000-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="9d000-195">Нормальный</span><span class="sxs-lookup"><span data-stu-id="9d000-195">Normal</span></span>

  <span data-ttu-id="9d000-196">Это состояние оживляет заливку эллипса, восстанавливая его в `Background` цвете управления.</span><span class="sxs-lookup"><span data-stu-id="9d000-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="9d000-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9d000-197">MouseOver</span></span>

  <span data-ttu-id="9d000-198">Это состояние оживляет `Background` цвет эллипса `Yellow`к новому цвету: .</span><span class="sxs-lookup"><span data-stu-id="9d000-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="9d000-199">\*\* \<>ControlTemplate\*\* теперь должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9d000-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="9d000-200">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="9d000-200">Run the project.</span></span> <span data-ttu-id="9d000-201">Обратите внимание, что при перемещении мыши по кнопке цвет \*\* \<Эллипса>\*\* оживляет.</span><span class="sxs-lookup"><span data-stu-id="9d000-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![мышь перемещается по кнопке WPF, чтобы изменить цвет заполнения](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="9d000-203">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9d000-203">Next steps</span></span>

- [<span data-ttu-id="9d000-204">Создание стиля для управления в WPF</span><span class="sxs-lookup"><span data-stu-id="9d000-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="9d000-205">Стили и шаблоны в WPF</span><span class="sxs-lookup"><span data-stu-id="9d000-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9d000-206">Обзор ресурсов XAML</span><span class="sxs-lookup"><span data-stu-id="9d000-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
