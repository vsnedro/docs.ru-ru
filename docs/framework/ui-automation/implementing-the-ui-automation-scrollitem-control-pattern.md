---
title: Реализация шаблона элемента управления ScrollItem модели автоматизации пользовательского интерфейса
description: Ознакомьтесь с правилами и соглашениями по реализации шаблона элемента управления Скроллитем в модели автоматизации пользовательского интерфейса. См. раздел обязательные элементы для интерфейса Искроллитемпровидер.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: a548eb25280d9a8feddc4633a1ba3e7dc022af36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163569"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="ab20e-104">Реализация шаблона элемента управления ScrollItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ab20e-104">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ab20e-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="ab20e-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ab20e-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ab20e-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ab20e-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IScrollItemProvider>, включая сведения о свойствах, методах и событиях.</span><span class="sxs-lookup"><span data-stu-id="ab20e-107">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="ab20e-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="ab20e-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ab20e-109">Шаблон элемента управления <xref:System.Windows.Automation.ScrollItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="ab20e-109">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="ab20e-110">Этот шаблон элемента управления действует как отдельный канал связи между дочерним элементом управления и его контейнером, чтобы контейнер гарантированно мог изменять видимое в настоящий момент содержимое (или область) в его области просмотра для отображения дочернего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ab20e-110">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="ab20e-111">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ab20e-111">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ab20e-112">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="ab20e-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ab20e-113">При реализации шаблона элемента управления ScrollItem обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="ab20e-113">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ab20e-114">Не требуется, чтобы элементы, содержащиеся в элементе управления "Окно" или "Полотно", реализовывали интерфейс IScrollItemProvider.</span><span class="sxs-lookup"><span data-stu-id="ab20e-114">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="ab20e-115">Однако в качестве альтернативы они должны предоставлять действительное расположение для <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="ab20e-115">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="ab20e-116">Это позволит клиентскому приложению модели автоматизации пользовательского интерфейса использовать методы шаблона элемента управления <xref:System.Windows.Automation.ScrollPattern> в контейнере для отображения дочернего элемента шаблона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ab20e-116">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="ab20e-117">Обязательные члены для IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="ab20e-117">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="ab20e-118">Следующий метод является обязательным для реализации интерфейса IScrollProvider.</span><span class="sxs-lookup"><span data-stu-id="ab20e-118">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="ab20e-119">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="ab20e-119">Required members</span></span>|<span data-ttu-id="ab20e-120">Тип члена</span><span class="sxs-lookup"><span data-stu-id="ab20e-120">Member type</span></span>|<span data-ttu-id="ab20e-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab20e-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="ab20e-122">-Method</span><span class="sxs-lookup"><span data-stu-id="ab20e-122">-   Method</span></span>|<span data-ttu-id="ab20e-123">Нет</span><span class="sxs-lookup"><span data-stu-id="ab20e-123">None</span></span>|  
  
 <span data-ttu-id="ab20e-124">Этот шаблон элемента управления не имеет связанных свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="ab20e-124">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="ab20e-125">Исключения</span><span class="sxs-lookup"><span data-stu-id="ab20e-125">Exceptions</span></span>  
 <span data-ttu-id="ab20e-126">Поставщики должны вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="ab20e-126">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="ab20e-127">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="ab20e-127">Exception Type</span></span>|<span data-ttu-id="ab20e-128">Условие</span><span class="sxs-lookup"><span data-stu-id="ab20e-128">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="ab20e-129">Если элемент не может быть прокручен в представлении:</span><span class="sxs-lookup"><span data-stu-id="ab20e-129">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="ab20e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ab20e-130">See also</span></span>

- [<span data-ttu-id="ab20e-131">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ab20e-131">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ab20e-132">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ab20e-132">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ab20e-133">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="ab20e-133">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ab20e-134">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ab20e-134">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ab20e-135">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ab20e-135">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
