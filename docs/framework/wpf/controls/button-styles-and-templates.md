---
title: Стили и шаблоны элемента Button
description: Сведения о стилях и шаблонах для элемента управления "Кнопка" Windows Presentation Foundation. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 11509adeef397f26eb040e6e98d0edb333b2515f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166260"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="513d5-104">Стили и шаблоны элемента Button</span><span class="sxs-lookup"><span data-stu-id="513d5-104">Button Styles and Templates</span></span>
<span data-ttu-id="513d5-105">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="513d5-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="513d5-106">Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="513d5-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="513d5-107">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="513d5-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="513d5-108">Части кнопки</span><span class="sxs-lookup"><span data-stu-id="513d5-108">Button Parts</span></span>  
 <span data-ttu-id="513d5-109"><xref:System.Windows.Controls.Button>Элемент управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="513d5-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="513d5-110">Состояния кнопок</span><span class="sxs-lookup"><span data-stu-id="513d5-110">Button States</span></span>  
 <span data-ttu-id="513d5-111">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="513d5-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="513d5-112">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="513d5-112">VisualState Name</span></span>|<span data-ttu-id="513d5-113">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="513d5-113">VisualStateGroup Name</span></span>|<span data-ttu-id="513d5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="513d5-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="513d5-115">Норм.</span><span class="sxs-lookup"><span data-stu-id="513d5-115">Normal</span></span>|<span data-ttu-id="513d5-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="513d5-116">CommonStates</span></span>|<span data-ttu-id="513d5-117">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="513d5-117">The default state.</span></span>|  
|<span data-ttu-id="513d5-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="513d5-118">MouseOver</span></span>|<span data-ttu-id="513d5-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="513d5-119">CommonStates</span></span>|<span data-ttu-id="513d5-120">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="513d5-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="513d5-121">Нажато</span><span class="sxs-lookup"><span data-stu-id="513d5-121">Pressed</span></span>|<span data-ttu-id="513d5-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="513d5-122">CommonStates</span></span>|<span data-ttu-id="513d5-123">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="513d5-123">The control is pressed.</span></span>|  
|<span data-ttu-id="513d5-124">Отключено</span><span class="sxs-lookup"><span data-stu-id="513d5-124">Disabled</span></span>|<span data-ttu-id="513d5-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="513d5-125">CommonStates</span></span>|<span data-ttu-id="513d5-126">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="513d5-126">The control is disabled.</span></span>|  
|<span data-ttu-id="513d5-127">Focused</span><span class="sxs-lookup"><span data-stu-id="513d5-127">Focused</span></span>|<span data-ttu-id="513d5-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="513d5-128">FocusStates</span></span>|<span data-ttu-id="513d5-129">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="513d5-129">The control has focus.</span></span>|  
|<span data-ttu-id="513d5-130">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="513d5-130">Unfocused</span></span>|<span data-ttu-id="513d5-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="513d5-131">FocusStates</span></span>|<span data-ttu-id="513d5-132">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="513d5-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="513d5-133">Допустимо</span><span class="sxs-lookup"><span data-stu-id="513d5-133">Valid</span></span>|<span data-ttu-id="513d5-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="513d5-134">ValidationStates</span></span>|<span data-ttu-id="513d5-135">Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .</span><span class="sxs-lookup"><span data-stu-id="513d5-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="513d5-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="513d5-136">InvalidFocused</span></span>|<span data-ttu-id="513d5-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="513d5-137">ValidationStates</span></span>|<span data-ttu-id="513d5-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="513d5-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="513d5-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="513d5-139">InvalidUnfocused</span></span>|<span data-ttu-id="513d5-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="513d5-140">ValidationStates</span></span>|<span data-ttu-id="513d5-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="513d5-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="513d5-142">Пример ControlTemplate для кнопки</span><span class="sxs-lookup"><span data-stu-id="513d5-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="513d5-143">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="513d5-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="513d5-144">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="513d5-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="513d5-145">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="513d5-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="513d5-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="513d5-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="513d5-147">Стили и шаблоны элемента Control</span><span class="sxs-lookup"><span data-stu-id="513d5-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="513d5-148">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="513d5-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="513d5-149">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="513d5-149">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="513d5-150">Создание шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="513d5-150">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
