---
title: Стили и шаблоны элемента TextBox
description: Сведения о стилях и шаблонах для элемента управления TextBox Windows Presentation Foundation. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164736"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="73f4b-104">Стили и шаблоны элемента TextBox</span><span class="sxs-lookup"><span data-stu-id="73f4b-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="73f4b-105">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="73f4b-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="73f4b-106">Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="73f4b-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="73f4b-107">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="73f4b-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="73f4b-108">Части текстового поля</span><span class="sxs-lookup"><span data-stu-id="73f4b-108">TextBox Parts</span></span>  
 <span data-ttu-id="73f4b-109">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="73f4b-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="73f4b-110">Часть</span><span class="sxs-lookup"><span data-stu-id="73f4b-110">Part</span></span>|<span data-ttu-id="73f4b-111">Тип</span><span class="sxs-lookup"><span data-stu-id="73f4b-111">Type</span></span>|<span data-ttu-id="73f4b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="73f4b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="73f4b-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="73f4b-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="73f4b-114">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="73f4b-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="73f4b-115">Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="73f4b-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="73f4b-116">Состояния текстового поля</span><span class="sxs-lookup"><span data-stu-id="73f4b-116">TextBox States</span></span>  
 <span data-ttu-id="73f4b-117">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="73f4b-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="73f4b-118">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="73f4b-118">VisualState Name</span></span>|<span data-ttu-id="73f4b-119">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="73f4b-119">VisualStateGroup Name</span></span>|<span data-ttu-id="73f4b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="73f4b-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="73f4b-121">Норм.</span><span class="sxs-lookup"><span data-stu-id="73f4b-121">Normal</span></span>|<span data-ttu-id="73f4b-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-122">CommonStates</span></span>|<span data-ttu-id="73f4b-123">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73f4b-123">The default state.</span></span>|  
|<span data-ttu-id="73f4b-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="73f4b-124">MouseOver</span></span>|<span data-ttu-id="73f4b-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-125">CommonStates</span></span>|<span data-ttu-id="73f4b-126">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="73f4b-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="73f4b-127">Отключено</span><span class="sxs-lookup"><span data-stu-id="73f4b-127">Disabled</span></span>|<span data-ttu-id="73f4b-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-128">CommonStates</span></span>|<span data-ttu-id="73f4b-129">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="73f4b-129">The control is disabled.</span></span>|  
|<span data-ttu-id="73f4b-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="73f4b-130">ReadOnly</span></span>|<span data-ttu-id="73f4b-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-131">CommonStates</span></span>|<span data-ttu-id="73f4b-132">Пользователь не может изменить текст в <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="73f4b-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="73f4b-133">Focused</span><span class="sxs-lookup"><span data-stu-id="73f4b-133">Focused</span></span>|<span data-ttu-id="73f4b-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-134">FocusStates</span></span>|<span data-ttu-id="73f4b-135">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="73f4b-135">The control has focus.</span></span>|  
|<span data-ttu-id="73f4b-136">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="73f4b-136">Unfocused</span></span>|<span data-ttu-id="73f4b-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-137">FocusStates</span></span>|<span data-ttu-id="73f4b-138">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="73f4b-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="73f4b-139">Допустимо</span><span class="sxs-lookup"><span data-stu-id="73f4b-139">Valid</span></span>|<span data-ttu-id="73f4b-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-140">ValidationStates</span></span>|<span data-ttu-id="73f4b-141">Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .</span><span class="sxs-lookup"><span data-stu-id="73f4b-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="73f4b-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="73f4b-142">InvalidFocused</span></span>|<span data-ttu-id="73f4b-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-143">ValidationStates</span></span>|<span data-ttu-id="73f4b-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет `true` фокус.</span><span class="sxs-lookup"><span data-stu-id="73f4b-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="73f4b-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="73f4b-145">InvalidUnfocused</span></span>|<span data-ttu-id="73f4b-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="73f4b-146">ValidationStates</span></span>|<span data-ttu-id="73f4b-147"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство `true` имеет элемент управления, не имеющий фокуса.</span><span class="sxs-lookup"><span data-stu-id="73f4b-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="73f4b-148">Пример ControlTemplate для TextBox</span><span class="sxs-lookup"><span data-stu-id="73f4b-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="73f4b-149">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="73f4b-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="73f4b-150">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="73f4b-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="73f4b-151">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="73f4b-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f4b-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73f4b-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="73f4b-153">Стили и шаблоны элемента Control</span><span class="sxs-lookup"><span data-stu-id="73f4b-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="73f4b-154">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="73f4b-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="73f4b-155">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="73f4b-155">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="73f4b-156">Создание шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="73f4b-156">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
