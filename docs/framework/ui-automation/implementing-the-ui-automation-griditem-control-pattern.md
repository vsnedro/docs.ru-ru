---
title: Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
description: Сведения о правилах и соглашениях для реализации шаблона элемента управления Гридитемпаттерн для элементов сетки в модели автоматизации пользовательского интерфейса. См. раздел обязательные элементы для Игридитемпровидер.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: e0a0c616f3f0cf9bc091e4fbb496d71ab8550bd3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165819"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="5405b-104">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5405b-104">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="5405b-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="5405b-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5405b-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="5405b-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="5405b-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>, включая сведения о свойствах.</span><span class="sxs-lookup"><span data-stu-id="5405b-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="5405b-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="5405b-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="5405b-109">Шаблон элемента управления <xref:System.Windows.Automation.GridItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="5405b-109">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="5405b-110">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="5405b-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="5405b-111">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="5405b-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="5405b-112">При реализации <xref:System.Windows.Automation.Provider.IGridProvider> обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="5405b-112">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="5405b-113">Координаты сетки отсчитываются от нуля, начиная с верхней левой ячейки с координатами (0, 0).</span><span class="sxs-lookup"><span data-stu-id="5405b-113">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="5405b-114">Объединенные ячейки будут передавать свои свойства <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> и <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> на основе свойств их базовой ячейки привязки в соответствии с определением в поставщике автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5405b-114">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="5405b-115">Как правило, это будет самая верхняя строка и крайний левый столбец.</span><span class="sxs-lookup"><span data-stu-id="5405b-115">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="5405b-116"><xref:System.Windows.Automation.Provider.IGridItemProvider> не предусматривает активные манипуляции с сеткой, такие как объединение или разбиение ячеек.</span><span class="sxs-lookup"><span data-stu-id="5405b-116"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="5405b-117">Элементы управления, реализующие <xref:System.Windows.Automation.Provider.IGridItemProvider>, обычно могут быть пройдены (то есть клиент автоматизации пользовательского интерфейса может переходить в соседние элементы управления) с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="5405b-117">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="5405b-118">Обязательные члены для IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="5405b-118">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="5405b-119">Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="5405b-119">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="5405b-120">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="5405b-120">Required members</span></span>|<span data-ttu-id="5405b-121">Тип члена</span><span class="sxs-lookup"><span data-stu-id="5405b-121">Member type</span></span>|<span data-ttu-id="5405b-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="5405b-122">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="5405b-123">Свойство</span><span class="sxs-lookup"><span data-stu-id="5405b-123">Property</span></span>|<span data-ttu-id="5405b-124">None</span><span class="sxs-lookup"><span data-stu-id="5405b-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="5405b-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="5405b-125">Property</span></span>|<span data-ttu-id="5405b-126">None</span><span class="sxs-lookup"><span data-stu-id="5405b-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="5405b-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="5405b-127">Property</span></span>|<span data-ttu-id="5405b-128">None</span><span class="sxs-lookup"><span data-stu-id="5405b-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="5405b-129">Свойство</span><span class="sxs-lookup"><span data-stu-id="5405b-129">Property</span></span>|<span data-ttu-id="5405b-130">None</span><span class="sxs-lookup"><span data-stu-id="5405b-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="5405b-131">Свойство</span><span class="sxs-lookup"><span data-stu-id="5405b-131">Property</span></span>|<span data-ttu-id="5405b-132">None</span><span class="sxs-lookup"><span data-stu-id="5405b-132">None</span></span>|  
  
 <span data-ttu-id="5405b-133">Этот шаблон элемента управления не имеет связанных методов или событий.</span><span class="sxs-lookup"><span data-stu-id="5405b-133">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="5405b-134">Исключения</span><span class="sxs-lookup"><span data-stu-id="5405b-134">Exceptions</span></span>  
 <span data-ttu-id="5405b-135">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="5405b-135">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5405b-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5405b-136">See also</span></span>

- [<span data-ttu-id="5405b-137">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5405b-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="5405b-138">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5405b-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="5405b-139">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="5405b-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="5405b-140">Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5405b-140">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="5405b-141">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5405b-141">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="5405b-142">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5405b-142">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
