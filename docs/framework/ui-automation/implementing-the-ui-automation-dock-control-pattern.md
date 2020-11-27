---
title: Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса Dock
description: Узнайте, как реализовать шаблон элемента управления "закрепление модели автоматизации пользовательского интерфейса". Используйте шаблон элемента управления Доккпаттерн для предоставления свойств элемента управления Dock. Реализуйте IDockProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: 769808b190ade33ae52c53e03e1b4f77d4439df1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269630"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a><span data-ttu-id="bb105-105">Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса Dock</span><span class="sxs-lookup"><span data-stu-id="bb105-105">Implementing the UI Automation Dock Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="bb105-106">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="bb105-106">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bb105-107">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="bb105-107">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="bb105-108">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IDockProvider>, включая сведения о свойствах.</span><span class="sxs-lookup"><span data-stu-id="bb105-108">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IDockProvider>, including information about properties.</span></span> <span data-ttu-id="bb105-109">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="bb105-109">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="bb105-110">Шаблон элемента управления <xref:System.Windows.Automation.DockPattern> используется для предоставления свойств закрепления элемента управления в контейнере закрепления.</span><span class="sxs-lookup"><span data-stu-id="bb105-110">The <xref:System.Windows.Automation.DockPattern> control pattern is used to expose the dock properties of a control within a docking container.</span></span> <span data-ttu-id="bb105-111">Контейнер закрепления — это элемент управления, который позволяет упорядочить дочерние элементы по горизонтали и по вертикали друг относительно друга.</span><span class="sxs-lookup"><span data-stu-id="bb105-111">A docking container is a control that allows you to arrange child elements horizontally and vertically, relative to each other.</span></span> <span data-ttu-id="bb105-112">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bb105-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
 <span data-ttu-id="bb105-113">![Доковый контейнер с двумя доковыми дочерними элементами.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span><span class="sxs-lookup"><span data-stu-id="bb105-113">![Docking container with two docked children.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span></span>  
<span data-ttu-id="bb105-114">Пример закрепления из Visual Studio, где окно "Представление классов" — DockPosition.Right, а окно "Список ошибок" — DockPosition.Bottom</span><span class="sxs-lookup"><span data-stu-id="bb105-114">Docking Example from Visual Studio Where "Class View" Window Is DockPosition.Right and "Error List" Window Is DockPosition.Bottom</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="bb105-115">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="bb105-115">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="bb105-116">При реализации шаблона элемента управления Dock обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="bb105-116">When implementing the Dock control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="bb105-117"><xref:System.Windows.Automation.Provider.IDockProvider> не предоставляет какие-либо свойства контейнера закрепления или какие-либо свойства элементов управления, закрепленных рядом с текущим элементом управления в контейнере закрепления.</span><span class="sxs-lookup"><span data-stu-id="bb105-117"><xref:System.Windows.Automation.Provider.IDockProvider> does not expose any properties of the docking container or any properties of controls that are docked adjacent to the current control within the docking container.</span></span>  
  
- <span data-ttu-id="bb105-118">Элементы управления закрепляются относительно друг друга в зависимости от их текущего z-порядка; чем больше z-порядок расположения, тем дальше они размещены от заданного края контейнера закрепления.</span><span class="sxs-lookup"><span data-stu-id="bb105-118">Controls are docked relative to each other based on their current z-order; the higher their z-order placement, the farther they are placed from the specified edge of the docking container.</span></span>  
  
- <span data-ttu-id="bb105-119">При изменении размеров контейнера закрепления все закрепленные элементы управления в контейнере будут перенесены с выравниванием по тому же краю, к которому они были первоначально прикреплены.</span><span class="sxs-lookup"><span data-stu-id="bb105-119">If the docking container is resized, any docked controls within the container will be repositioned flush to the same edge to which they were originally docked.</span></span> <span data-ttu-id="bb105-120">Размеры закрепленных элементов управления также будут изменены для заполнения пробелов в контейнере согласно поведению закрепления их <xref:System.Windows.Automation.DockPosition>.</span><span class="sxs-lookup"><span data-stu-id="bb105-120">The docked controls will also resize to fill any space within the container according to the docking behavior of their <xref:System.Windows.Automation.DockPosition>.</span></span> <span data-ttu-id="bb105-121">Например, если указано <xref:System.Windows.Automation.DockPosition.Top> , левая и правая стороны элемента управления будут расширены для заполнения всего доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="bb105-121">For example, if <xref:System.Windows.Automation.DockPosition.Top> is specified, the left and right sides of the control will expand to fill any available space.</span></span> <span data-ttu-id="bb105-122">Если указано <xref:System.Windows.Automation.DockPosition.Fill> , все четыре стороны элемента управления будут расширены для заполнения всего доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="bb105-122">If <xref:System.Windows.Automation.DockPosition.Fill> is specified, all four sides of the control will expand to fill any available space.</span></span>  
  
- <span data-ttu-id="bb105-123">На системах с несколькими мониторами элементы управления должны закрепляться с левой или правой стороны текущего монитора.</span><span class="sxs-lookup"><span data-stu-id="bb105-123">On a multi-monitor system, controls should dock to the left or right side of the current monitor.</span></span> <span data-ttu-id="bb105-124">Если это невозможно, они должны закрепляться с левой стороны крайнего левого монитора или с правой стороны крайнего правого монитора.</span><span class="sxs-lookup"><span data-stu-id="bb105-124">If that is not possible, they should dock to the left side of the leftmost monitor or the right side of the rightmost monitor.</span></span>  
  
<a name="Required_Members_for_IDockProvider"></a>

## <a name="required-members-for-idockprovider"></a><span data-ttu-id="bb105-125">Обязательные члены для IDockProvider</span><span class="sxs-lookup"><span data-stu-id="bb105-125">Required Members for IDockProvider</span></span>  

 <span data-ttu-id="bb105-126">Следующие свойства и методы обязательны для реализации интерфейса IDockProvider.</span><span class="sxs-lookup"><span data-stu-id="bb105-126">The following properties and methods are required for implementing the IDockProvider interface.</span></span>  
  
|<span data-ttu-id="bb105-127">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="bb105-127">Required members</span></span>|<span data-ttu-id="bb105-128">Тип члена</span><span class="sxs-lookup"><span data-stu-id="bb105-128">Member type</span></span>|<span data-ttu-id="bb105-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb105-129">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|<span data-ttu-id="bb105-130">Свойство.</span><span class="sxs-lookup"><span data-stu-id="bb105-130">Property</span></span>|<span data-ttu-id="bb105-131">Нет</span><span class="sxs-lookup"><span data-stu-id="bb105-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|<span data-ttu-id="bb105-132">Метод</span><span class="sxs-lookup"><span data-stu-id="bb105-132">Method</span></span>|<span data-ttu-id="bb105-133">Нет</span><span class="sxs-lookup"><span data-stu-id="bb105-133">None</span></span>|  
  
 <span data-ttu-id="bb105-134">Этот шаблон элемента управления не имеет связанных событий.</span><span class="sxs-lookup"><span data-stu-id="bb105-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="bb105-135">Исключения</span><span class="sxs-lookup"><span data-stu-id="bb105-135">Exceptions</span></span>  

 <span data-ttu-id="bb105-136">Поставщики должны вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="bb105-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="bb105-137">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="bb105-137">Exception type</span></span>|<span data-ttu-id="bb105-138">Условие</span><span class="sxs-lookup"><span data-stu-id="bb105-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> <span data-ttu-id="bb105-139">— Когда элемент управления не может выполнить запрошенный стиль закрепления.</span><span class="sxs-lookup"><span data-stu-id="bb105-139">-   When a control is not able to execute the requested dock style.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb105-140">См. также</span><span class="sxs-lookup"><span data-stu-id="bb105-140">See also</span></span>

- [<span data-ttu-id="bb105-141">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb105-141">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="bb105-142">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb105-142">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="bb105-143">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="bb105-143">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="bb105-144">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb105-144">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="bb105-145">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb105-145">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
