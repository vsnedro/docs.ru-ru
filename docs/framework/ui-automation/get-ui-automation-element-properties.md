---
title: Получение свойств элементов управления модели автоматизации пользовательского интерфейса
description: См. инструкции и пример, демонстрирующий получение текущих или кэшированных свойств элемента модели автоматизации пользовательского интерфейса.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 34a42355acce0beafbb9658baf6032e4e7e19fcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276429"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="00696-103">Получение свойств элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="00696-103">Get UI Automation Element Properties</span></span>

> [!NOTE]
> <span data-ttu-id="00696-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="00696-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="00696-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="00696-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="00696-106">В этом разделе показано, как получить свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента.</span><span class="sxs-lookup"><span data-stu-id="00696-106">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="00696-107">Получение значения текущего свойства</span><span class="sxs-lookup"><span data-stu-id="00696-107">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="00696-108">Получите объект, <xref:System.Windows.Automation.AutomationElement> свойство которого вы хотите получить.</span><span class="sxs-lookup"><span data-stu-id="00696-108">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="00696-109">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> или извлеките <xref:System.Windows.Automation.AutomationElement.Current%2A> структуру свойства и получите значение от одного из его членов.</span><span class="sxs-lookup"><span data-stu-id="00696-109">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="00696-110">Получение значения кэшированного свойства</span><span class="sxs-lookup"><span data-stu-id="00696-110">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="00696-111">Получите объект, <xref:System.Windows.Automation.AutomationElement> свойство которого вы хотите получить.</span><span class="sxs-lookup"><span data-stu-id="00696-111">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="00696-112">Свойство должно быть указано в <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="00696-112">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="00696-113">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> или извлеките <xref:System.Windows.Automation.AutomationElement.Cached%2A> структуру свойства и получите значение от одного из его членов.</span><span class="sxs-lookup"><span data-stu-id="00696-113">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00696-114">Пример</span><span class="sxs-lookup"><span data-stu-id="00696-114">Example</span></span>  

 <span data-ttu-id="00696-115">В следующем примере показаны различные способы получения текущих свойств <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="00696-115">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="00696-116">См. также</span><span class="sxs-lookup"><span data-stu-id="00696-116">See also</span></span>

- [<span data-ttu-id="00696-117">Свойства автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="00696-117">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="00696-118">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="00696-118">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="00696-119">Кэширование в клиентах автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="00696-119">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
