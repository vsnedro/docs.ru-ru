---
title: Реализация шаблона элементов управления модели автоматизации пользовательского интерфейса Toggle
description: Ознакомьтесь с правилами и соглашениями по реализации шаблона элемента управления Toggle в модели автоматизации пользовательского интерфейса. Знание обязательных членов для интерфейса IToggleProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: f9ae850a560101582b5f1a461de19f260ef59798
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168037"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="ca772-104">Реализация шаблона элементов управления модели автоматизации пользовательского интерфейса Toggle</span><span class="sxs-lookup"><span data-stu-id="ca772-104">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ca772-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="ca772-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ca772-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ca772-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ca772-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IToggleProvider>, включая сведения о методах и свойствах.</span><span class="sxs-lookup"><span data-stu-id="ca772-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="ca772-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="ca772-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ca772-109"><xref:System.Windows.Automation.TogglePattern> Шаблон элемента управления используется для поддержки элементов управления, которые можно переключать между разными состояниями и поддерживать состояние после установки.</span><span class="sxs-lookup"><span data-stu-id="ca772-109">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="ca772-110">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ca772-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ca772-111">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="ca772-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ca772-112">При реализации шаблона элемента управления Toggle обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="ca772-112">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ca772-113">Элементы управления, которые не поддерживают состояние при активации, такие как кнопки, кнопки панели инструментов и гиперссылки, вместо этого шаблона должны реализовывать <xref:System.Windows.Automation.Provider.IInvokeProvider> .</span><span class="sxs-lookup"><span data-stu-id="ca772-113">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="ca772-114">Элемент управления должен проходить по его <xref:System.Windows.Automation.ToggleState> в следующем порядке: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> и если поддерживается — <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="ca772-114">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="ca772-115"><xref:System.Windows.Automation.TogglePattern> не предоставляет метод SetState(newState) из-за проблем, окружающих прямую установку флажка с тремя состояниями без прохода по его соответствующей последовательности <xref:System.Windows.Automation.ToggleState> .</span><span class="sxs-lookup"><span data-stu-id="ca772-115"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="ca772-116">Элемент управления RadioButton не реализует <xref:System.Windows.Automation.Provider.IToggleProvider>, так как он не способен пройти по его допустимым состояниям.</span><span class="sxs-lookup"><span data-stu-id="ca772-116">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="ca772-117">Обязательные члены для IToggleProvider</span><span class="sxs-lookup"><span data-stu-id="ca772-117">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="ca772-118">Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IToggleProvider>.</span><span class="sxs-lookup"><span data-stu-id="ca772-118">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="ca772-119">Обязательный член</span><span class="sxs-lookup"><span data-stu-id="ca772-119">Required member</span></span>|<span data-ttu-id="ca772-120">Тип члена</span><span class="sxs-lookup"><span data-stu-id="ca772-120">Member type</span></span>|<span data-ttu-id="ca772-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca772-121">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="ca772-122">Метод</span><span class="sxs-lookup"><span data-stu-id="ca772-122">Method</span></span>|<span data-ttu-id="ca772-123">None</span><span class="sxs-lookup"><span data-stu-id="ca772-123">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="ca772-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="ca772-124">Property</span></span>|<span data-ttu-id="ca772-125">None</span><span class="sxs-lookup"><span data-stu-id="ca772-125">None</span></span>|  
  
 <span data-ttu-id="ca772-126">Этот шаблон элемента управления не имеет связанных событий.</span><span class="sxs-lookup"><span data-stu-id="ca772-126">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="ca772-127">Исключения</span><span class="sxs-lookup"><span data-stu-id="ca772-127">Exceptions</span></span>  
 <span data-ttu-id="ca772-128">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="ca772-128">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca772-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca772-129">See also</span></span>

- [<span data-ttu-id="ca772-130">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ca772-130">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ca772-131">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ca772-131">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ca772-132">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="ca772-132">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ca772-133">Получение состояния флажка с использованием автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ca772-133">Get the Toggle State of a Check Box Using UI Automation</span></span>](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="ca772-134">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ca772-134">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ca772-135">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ca772-135">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
