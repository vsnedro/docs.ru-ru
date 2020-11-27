---
title: Реализация шаблона элемента управления преобразованиями модели автоматизации пользовательского интерфейса
description: Ознакомьтесь с правилами и соглашениями для реализации шаблона элемента управления Transform в модели автоматизации пользовательского интерфейса. Знание обязательных членов для интерфейса Итрансформпровидер.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: fc47170a08ff08f6cd8f67996ef8fbf19c40f819
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265652"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="e3599-104">Реализация шаблона элемента управления преобразованиями модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e3599-104">Implementing the UI Automation Transform Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="e3599-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="e3599-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e3599-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e3599-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e3599-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITransformProvider>, включая сведения о свойствах, методах и событиях.</span><span class="sxs-lookup"><span data-stu-id="e3599-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="e3599-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="e3599-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="e3599-109">Шаблон элемента управления <xref:System.Windows.Automation.TransformPattern> используется для поддержки элементов управления, которые можно перемещать, поворачивать или изменять их размер в двумерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="e3599-109">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="e3599-110">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e3599-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="e3599-111">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="e3599-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="e3599-112">При реализации шаблона элемента управления Transform обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="e3599-112">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="e3599-113">Поддержка этого шаблона элемента управления не ограничена объектами на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="e3599-113">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="e3599-114">Этот шаблон элемента управления также должен поддерживаться дочерними элементами объекта контейнера, если эти дочерние элементы можно перемещать, изменять их размер или свободно поворачивать в пределах контейнера.</span><span class="sxs-lookup"><span data-stu-id="e3599-114">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="e3599-115">Объект нельзя перемещать, изменять его размер или поворачивать таким образом, что его итоговое положение на экране окажется полностью вне координат своего контейнера и поэтому он станет недоступным для клавиатуры или мыши (например, когда окно верхнего уровня перемещается за пределы экрана или дочерний объект перемещается за пределы границ окна просмотра контейнера).</span><span class="sxs-lookup"><span data-stu-id="e3599-115">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="e3599-116">В этих случаях объект помещается максимально близко к запрошенным экранным координатам с переопределением верхней или левой координаты, чтобы они находились в границах контейнера.</span><span class="sxs-lookup"><span data-stu-id="e3599-116">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="e3599-117">Для систем с несколькими мониторами при перемещении объекта, изменении его размера или повороте полностью за пределами координат объединенного рабочего стола объект помещается на основном мониторе максимально близко к запрошенным координатам.</span><span class="sxs-lookup"><span data-stu-id="e3599-117">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="e3599-118">Все параметры и значения свойств являются абсолютными и не зависят от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="e3599-118">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="e3599-119">Обязательные члены для ITransformProvider</span><span class="sxs-lookup"><span data-stu-id="e3599-119">Required Members for ITransformProvider</span></span>  

 <span data-ttu-id="e3599-120">Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.ITransformProvider>.</span><span class="sxs-lookup"><span data-stu-id="e3599-120">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="e3599-121">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="e3599-121">Required members</span></span>|<span data-ttu-id="e3599-122">Тип члена</span><span class="sxs-lookup"><span data-stu-id="e3599-122">Member type</span></span>|<span data-ttu-id="e3599-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3599-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="e3599-124">Свойство.</span><span class="sxs-lookup"><span data-stu-id="e3599-124">Property</span></span>|<span data-ttu-id="e3599-125">Нет</span><span class="sxs-lookup"><span data-stu-id="e3599-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="e3599-126">Свойство.</span><span class="sxs-lookup"><span data-stu-id="e3599-126">Property</span></span>|<span data-ttu-id="e3599-127">Нет</span><span class="sxs-lookup"><span data-stu-id="e3599-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="e3599-128">Свойство.</span><span class="sxs-lookup"><span data-stu-id="e3599-128">Property</span></span>|<span data-ttu-id="e3599-129">Нет</span><span class="sxs-lookup"><span data-stu-id="e3599-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="e3599-130">Метод</span><span class="sxs-lookup"><span data-stu-id="e3599-130">Method</span></span>|<span data-ttu-id="e3599-131">Нет</span><span class="sxs-lookup"><span data-stu-id="e3599-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="e3599-132">Метод</span><span class="sxs-lookup"><span data-stu-id="e3599-132">Method</span></span>|<span data-ttu-id="e3599-133">Нет</span><span class="sxs-lookup"><span data-stu-id="e3599-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="e3599-134">Метод</span><span class="sxs-lookup"><span data-stu-id="e3599-134">Method</span></span>|<span data-ttu-id="e3599-135">Нет</span><span class="sxs-lookup"><span data-stu-id="e3599-135">None</span></span>|  
  
 <span data-ttu-id="e3599-136">Этот шаблон элемента управления не имеет связанных событий.</span><span class="sxs-lookup"><span data-stu-id="e3599-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="e3599-137">Исключения</span><span class="sxs-lookup"><span data-stu-id="e3599-137">Exceptions</span></span>  

 <span data-ttu-id="e3599-138">Поставщики должны вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="e3599-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="e3599-139">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="e3599-139">Exception Type</span></span>|<span data-ttu-id="e3599-140">Условие</span><span class="sxs-lookup"><span data-stu-id="e3599-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="e3599-141">— Если <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="e3599-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="e3599-142">— Если <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="e3599-142">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="e3599-143">— Если <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="e3599-143">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3599-144">См. также</span><span class="sxs-lookup"><span data-stu-id="e3599-144">See also</span></span>

- [<span data-ttu-id="e3599-145">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e3599-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="e3599-146">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e3599-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="e3599-147">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="e3599-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="e3599-148">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e3599-148">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="e3599-149">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e3599-149">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
