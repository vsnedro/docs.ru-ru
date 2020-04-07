---
title: Стили и шаблоны элемента ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805911"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="9bb7a-102">Стили и шаблоны элемента ToggleButton</span><span class="sxs-lookup"><span data-stu-id="9bb7a-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="9bb7a-103">Эта тема описывает стили и <xref:System.Windows.Controls.Primitives.ToggleButton> шаблоны для управления.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="9bb7a-104">Вы можете изменить <xref:System.Windows.Controls.ControlTemplate> значение по умолчанию, чтобы придать элементу управления уникальный внешний вид.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9bb7a-105">Для получения дополнительной информации [см.](../../../desktop-wpf/themes/how-to-create-apply-template.md)</span><span class="sxs-lookup"><span data-stu-id="9bb7a-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="9bb7a-106">Части тглкиКнопка</span><span class="sxs-lookup"><span data-stu-id="9bb7a-106">ToggleButton Parts</span></span>

<span data-ttu-id="9bb7a-107">Элемент <xref:System.Windows.Controls.Primitives.ToggleButton> управления не имеет никаких названных частей.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="9bb7a-108">Состояния Тглгкстона</span><span class="sxs-lookup"><span data-stu-id="9bb7a-108">ToggleButton States</span></span>

<span data-ttu-id="9bb7a-109">В следующей таблице перечислены <xref:System.Windows.Controls.Primitives.ToggleButton> визуальные состояния для управления.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="9bb7a-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="9bb7a-110">VisualState Name</span></span>|<span data-ttu-id="9bb7a-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="9bb7a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9bb7a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9bb7a-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="9bb7a-113">Нормальный</span><span class="sxs-lookup"><span data-stu-id="9bb7a-113">Normal</span></span>|<span data-ttu-id="9bb7a-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-114">CommonStates</span></span>|<span data-ttu-id="9bb7a-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-115">The default state.</span></span>|
|<span data-ttu-id="9bb7a-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9bb7a-116">MouseOver</span></span>|<span data-ttu-id="9bb7a-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-117">CommonStates</span></span>|<span data-ttu-id="9bb7a-118">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="9bb7a-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="9bb7a-119">Pressed</span></span>|<span data-ttu-id="9bb7a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-120">CommonStates</span></span>|<span data-ttu-id="9bb7a-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-121">The control is pressed.</span></span>|
|<span data-ttu-id="9bb7a-122">Выключено</span><span class="sxs-lookup"><span data-stu-id="9bb7a-122">Disabled</span></span>|<span data-ttu-id="9bb7a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-123">CommonStates</span></span>|<span data-ttu-id="9bb7a-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-124">The control is disabled.</span></span>|
|<span data-ttu-id="9bb7a-125">Focused</span><span class="sxs-lookup"><span data-stu-id="9bb7a-125">Focused</span></span>|<span data-ttu-id="9bb7a-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-126">FocusStates</span></span>|<span data-ttu-id="9bb7a-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-127">The control has focus.</span></span>|
|<span data-ttu-id="9bb7a-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="9bb7a-128">Unfocused</span></span>|<span data-ttu-id="9bb7a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-129">FocusStates</span></span>|<span data-ttu-id="9bb7a-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-130">The control does not have focus.</span></span>|
|<span data-ttu-id="9bb7a-131">Флажок установлен</span><span class="sxs-lookup"><span data-stu-id="9bb7a-131">Checked</span></span>|<span data-ttu-id="9bb7a-132">Контрольные штаты</span><span class="sxs-lookup"><span data-stu-id="9bb7a-132">CheckStates</span></span>|<span data-ttu-id="9bb7a-133">Параметр <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равен `true`.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="9bb7a-134">Флажок снят.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-134">Unchecked</span></span>|<span data-ttu-id="9bb7a-135">Контрольные штаты</span><span class="sxs-lookup"><span data-stu-id="9bb7a-135">CheckStates</span></span>|<span data-ttu-id="9bb7a-136">Параметр <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равен `false`.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="9bb7a-137">Неопределенное</span><span class="sxs-lookup"><span data-stu-id="9bb7a-137">Indeterminate</span></span>|<span data-ttu-id="9bb7a-138">Контрольные штаты</span><span class="sxs-lookup"><span data-stu-id="9bb7a-138">CheckStates</span></span>|<span data-ttu-id="9bb7a-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> равно `true`, а <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равно `null`.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="9bb7a-140">Допустимо</span><span class="sxs-lookup"><span data-stu-id="9bb7a-140">Valid</span></span>|<span data-ttu-id="9bb7a-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-141">ValidationStates</span></span>|<span data-ttu-id="9bb7a-142">Элемент управления <xref:System.Windows.Controls.Validation> использует класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `false`прилагаемое свойство находится под контролем.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="9bb7a-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9bb7a-143">InvalidFocused</span></span>|<span data-ttu-id="9bb7a-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-144">ValidationStates</span></span>|<span data-ttu-id="9bb7a-145">Прилагаемое <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` свойство и элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="9bb7a-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9bb7a-146">InvalidUnfocused</span></span>|<span data-ttu-id="9bb7a-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9bb7a-147">ValidationStates</span></span>|<span data-ttu-id="9bb7a-148">Прилагаемое <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` свойство и элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="9bb7a-149">Если неопределенное визуальное состояние не существует в шаблоне управления, то неконтролируемое визуальное состояние будет использоваться в качестве визуального состояния по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="9bb7a-150">Пример управления тглочками</span><span class="sxs-lookup"><span data-stu-id="9bb7a-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="9bb7a-151">В следующем примере показано, <xref:System.Windows.Controls.Primitives.ToggleButton> как определить <xref:System.Windows.Controls.ControlTemplate> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="9bb7a-152">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9bb7a-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="9bb7a-153">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="9bb7a-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bb7a-154">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9bb7a-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9bb7a-155">Стили и шаблоны элемента Control</span><span class="sxs-lookup"><span data-stu-id="9bb7a-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9bb7a-156">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="9bb7a-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9bb7a-157">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="9bb7a-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9bb7a-158">Создание шаблона для управления</span><span class="sxs-lookup"><span data-stu-id="9bb7a-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
