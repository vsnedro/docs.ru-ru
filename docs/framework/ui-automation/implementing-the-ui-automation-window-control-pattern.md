---
title: Реализация шаблона элемента управления Window автоматизированного пользовательского интерфейса
description: Ознакомьтесь с правилами и соглашениями по реализации шаблона элемента управления Window в модели автоматизации пользовательского интерфейса. Знание обязательных членов для интерфейса IWindowProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: b43884393974e6f2863da6a4a5ca8f305e5a160c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286101"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="3ff77-104">Реализация шаблона элемента управления Window автоматизированного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3ff77-104">Implementing the UI Automation Window Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="3ff77-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="3ff77-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3ff77-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="3ff77-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3ff77-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IWindowProvider>, включая сведения о свойствах, методах и событиях <xref:System.Windows.Automation.WindowPattern> .</span><span class="sxs-lookup"><span data-stu-id="3ff77-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="3ff77-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="3ff77-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="3ff77-109"><xref:System.Windows.Automation.WindowPattern>Шаблон элемента управления используется для поддержки элементов управления, которые предоставляют фундаментальные функции на основе окна в традиционном графическом интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ff77-109">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional graphical user interface (GUI).</span></span> <span data-ttu-id="3ff77-110">Примеры элементов управления, которые должны реализовывать этот шаблон элемента управления, включают в себя окна приложений верхнего уровня, дочерние окна многодокументного интерфейса (MDI), элементы управления "область разделения" с изменяемыми размерами, модальные диалоговые окна и окна справки.</span><span class="sxs-lookup"><span data-stu-id="3ff77-110">Examples of controls that must implement this control pattern include top-level application windows, multiple-document interface (MDI) child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="3ff77-111">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="3ff77-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="3ff77-112">При реализации шаблона элемента управления Window обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="3ff77-112">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="3ff77-113">Для поддержки возможности изменения размера окна и его положения на экране с помощью модели автоматизации пользовательского интерфейса элемент управления должен реализовать <xref:System.Windows.Automation.Provider.ITransformProvider> в дополнение к <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="3ff77-113">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="3ff77-114">Элементы управления, содержащие заголовки окон и элементы этих заголовков, позволяющие перемещать, разворачивать, сворачивать, закрывать элемент управления или изменять его размер, обычно должны реализовывать <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="3ff77-114">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="3ff77-115">Такие элементы управления, как всплывающие подсказки, поля со списком или раскрывающиеся меню, обычно не реализуют <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="3ff77-115">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="3ff77-116">Окна всплывающей справки отличаются от обычных всплывающих подсказок тем, что предоставляют кнопку закрытия окна.</span><span class="sxs-lookup"><span data-stu-id="3ff77-116">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
- <span data-ttu-id="3ff77-117">IWindowProvider не поддерживает полноэкранный режим, так как он зависит от компонентов в приложении и не является типичным поведением окна.</span><span class="sxs-lookup"><span data-stu-id="3ff77-117">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>

## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="3ff77-118">Обязательные члены для IWindowProvider</span><span class="sxs-lookup"><span data-stu-id="3ff77-118">Required Members for IWindowProvider</span></span>  

 <span data-ttu-id="3ff77-119">Следующие свойства, методы и события обязательны для реализации интерфейса IWindowProvider.</span><span class="sxs-lookup"><span data-stu-id="3ff77-119">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="3ff77-120">Обязательный член</span><span class="sxs-lookup"><span data-stu-id="3ff77-120">Required member</span></span>|<span data-ttu-id="3ff77-121">Тип члена</span><span class="sxs-lookup"><span data-stu-id="3ff77-121">Member type</span></span>|<span data-ttu-id="3ff77-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ff77-122">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="3ff77-123">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3ff77-123">Property</span></span>|<span data-ttu-id="3ff77-124">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="3ff77-125">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3ff77-125">Property</span></span>|<span data-ttu-id="3ff77-126">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="3ff77-127">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3ff77-127">Property</span></span>|<span data-ttu-id="3ff77-128">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="3ff77-129">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3ff77-129">Property</span></span>|<span data-ttu-id="3ff77-130">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="3ff77-131">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3ff77-131">Property</span></span>|<span data-ttu-id="3ff77-132">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="3ff77-133">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3ff77-133">Property</span></span>|<span data-ttu-id="3ff77-134">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="3ff77-135">Метод</span><span class="sxs-lookup"><span data-stu-id="3ff77-135">Method</span></span>|<span data-ttu-id="3ff77-136">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="3ff77-137">Метод</span><span class="sxs-lookup"><span data-stu-id="3ff77-137">Method</span></span>|<span data-ttu-id="3ff77-138">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-138">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="3ff77-139">Метод</span><span class="sxs-lookup"><span data-stu-id="3ff77-139">Method</span></span>|<span data-ttu-id="3ff77-140">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="3ff77-141">Событие</span><span class="sxs-lookup"><span data-stu-id="3ff77-141">Event</span></span>|<span data-ttu-id="3ff77-142">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="3ff77-143">Событие</span><span class="sxs-lookup"><span data-stu-id="3ff77-143">Event</span></span>|<span data-ttu-id="3ff77-144">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff77-144">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="3ff77-145">Событие</span><span class="sxs-lookup"><span data-stu-id="3ff77-145">Event</span></span>|<span data-ttu-id="3ff77-146">Не гарантируется, что будет <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="3ff77-146">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="3ff77-147">Исключения</span><span class="sxs-lookup"><span data-stu-id="3ff77-147">Exceptions</span></span>  

 <span data-ttu-id="3ff77-148">Поставщики должны вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="3ff77-148">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="3ff77-149">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="3ff77-149">Exception type</span></span>|<span data-ttu-id="3ff77-150">Условие</span><span class="sxs-lookup"><span data-stu-id="3ff77-150">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="3ff77-151">— Если элемент управления не поддерживает запрошенное поведение.</span><span class="sxs-lookup"><span data-stu-id="3ff77-151">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="3ff77-152">— Если параметр не является допустимым числом.</span><span class="sxs-lookup"><span data-stu-id="3ff77-152">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ff77-153">См. также</span><span class="sxs-lookup"><span data-stu-id="3ff77-153">See also</span></span>

- [<span data-ttu-id="3ff77-154">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3ff77-154">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="3ff77-155">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3ff77-155">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="3ff77-156">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="3ff77-156">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="3ff77-157">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3ff77-157">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="3ff77-158">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3ff77-158">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
