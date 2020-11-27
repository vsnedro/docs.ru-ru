---
title: Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса
description: Ознакомьтесь с правилами и соглашениями для реализации шаблона элемента управления TableItem в модели автоматизации пользовательского интерфейса. Знание обязательных членов для интерфейса Итаблеитемпровидер.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 5e83f68772de3026fe8bcb265a11999e0b85a164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265678"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="fa645-104">Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-104">Implementing the UI Automation TableItem Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="fa645-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="fa645-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fa645-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="fa645-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="fa645-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITableItemProvider>, включая сведения о событиях и свойствах.</span><span class="sxs-lookup"><span data-stu-id="fa645-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="fa645-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="fa645-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="fa645-109">Шаблон элемента управления <xref:System.Windows.Automation.TableItemPattern> используется для поддержки дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="fa645-109">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="fa645-110">Доступ к функциям отдельной ячейки обеспечивается обязательной параллельной реализацией <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="fa645-110">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="fa645-111">Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IGridItemProvider> с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableItemProvider>, должен программными средствами предоставлять отношение между отдельной ячейкой и сведениями ее строки и столбца.</span><span class="sxs-lookup"><span data-stu-id="fa645-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="fa645-112">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="fa645-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="fa645-113">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="fa645-113">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="fa645-114">Сведения о связанных функциях элементов сетки см. [в разделе Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса](implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa645-114">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>

## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="fa645-115">Обязательные члены для ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="fa645-115">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="fa645-116">Обязательный член</span><span class="sxs-lookup"><span data-stu-id="fa645-116">Required member</span></span>|<span data-ttu-id="fa645-117">Тип члена</span><span class="sxs-lookup"><span data-stu-id="fa645-117">Member type</span></span>|<span data-ttu-id="fa645-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa645-118">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="fa645-119">Метод</span><span class="sxs-lookup"><span data-stu-id="fa645-119">Method</span></span>|<span data-ttu-id="fa645-120">Нет</span><span class="sxs-lookup"><span data-stu-id="fa645-120">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="fa645-121">Метод</span><span class="sxs-lookup"><span data-stu-id="fa645-121">Method</span></span>|<span data-ttu-id="fa645-122">Нет</span><span class="sxs-lookup"><span data-stu-id="fa645-122">None</span></span>|  
  
 <span data-ttu-id="fa645-123">Этот шаблон элемента управления не имеет связанных свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="fa645-123">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="fa645-124">Исключения</span><span class="sxs-lookup"><span data-stu-id="fa645-124">Exceptions</span></span>  

 <span data-ttu-id="fa645-125">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="fa645-125">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa645-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fa645-126">See also</span></span>

- [<span data-ttu-id="fa645-127">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-127">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="fa645-128">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-128">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="fa645-129">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="fa645-129">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="fa645-130">Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-130">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="fa645-131">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-131">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="fa645-132">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="fa645-133">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fa645-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
