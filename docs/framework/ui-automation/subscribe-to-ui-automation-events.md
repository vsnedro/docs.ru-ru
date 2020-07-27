---
title: Подписка на события модели автоматизации пользовательского интерфейса
description: См. раздел как подписываться на события, вызванные поставщиками автоматизации пользовательского интерфейса. В примере кода регистрируется обработчик событий для события, возникающего при вызове элемента управления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
ms.openlocfilehash: 8f456702657c70837c6137e3e60335110361bcd9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163537"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="c7c41-104">Подписка на события модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c7c41-104">Subscribe to UI Automation Events</span></span>
> [!NOTE]
> <span data-ttu-id="c7c41-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="c7c41-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c7c41-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="c7c41-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="c7c41-107">В этом разделе показано, как подписаться на события, вызванные поставщиками автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c7c41-107">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7c41-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c7c41-108">Example</span></span>  
 <span data-ttu-id="c7c41-109">В следующем примере кода регистрируется обработчик событий для события, которое возникает, когда элемент управления, например кнопки, вызывается и удаляется при закрытии формы приложения.</span><span class="sxs-lookup"><span data-stu-id="c7c41-109">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="c7c41-110">Событие идентифицируется по <xref:System.Windows.Automation.AutomationEvent>, переданному в качестве параметра в метод <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7c41-110">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="c7c41-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c7c41-111">Example</span></span>  
 <span data-ttu-id="c7c41-112">В следующем примере показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для подписки на событие, возникающее при изменении фокуса.</span><span class="sxs-lookup"><span data-stu-id="c7c41-112">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="c7c41-113">Выполняется отмена регистрации обработчика событий в методе, который может вызываться при завершении работы приложения, или когда уведомление о событиях пользовательского интерфейса больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="c7c41-113">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="c7c41-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7c41-114">See also</span></span>

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="c7c41-115">Обзор событий автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c7c41-115">UI Automation Events Overview</span></span>](ui-automation-events-overview.md)
