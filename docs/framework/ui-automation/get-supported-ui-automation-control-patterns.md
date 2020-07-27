---
title: Получение шаблонов элементов управления, поддерживающих модель автоматизации пользовательского интерфейса
description: Ознакомьтесь с примером, в котором показано, как получить поддерживаемые объекты шаблона элемента управления из элементов модели автоматизации пользовательского интерфейса.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: f2905b81a1af2f86c78b082f0241e2181c384d25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164157"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="8581e-103">Получение шаблонов элементов управления, поддерживающих модель автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8581e-103">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
> <span data-ttu-id="8581e-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="8581e-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8581e-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8581e-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8581e-106">В этом разделе показано, как получать объекты шаблона элемента управления из элементов [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8581e-106">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="8581e-107">Получение всех шаблонов элементов управления</span><span class="sxs-lookup"><span data-stu-id="8581e-107">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="8581e-108">Получите <xref:System.Windows.Automation.AutomationElement>, шаблоны элементов управления которого вас интересуют.</span><span class="sxs-lookup"><span data-stu-id="8581e-108">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="8581e-109">Вызовите метод <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>, чтобы получить все шаблоны элементов управления из этого элемента.</span><span class="sxs-lookup"><span data-stu-id="8581e-109">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="8581e-110">Настоятельно рекомендуется, чтобы клиент не использовал метод <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="8581e-110">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="8581e-111">Производительность может значительно снизиться, так как этот метод вызывает метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> внутренне для каждого существующего шаблона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8581e-111">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="8581e-112">Если это возможно, клиент должен вызывать метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> для основных интересующих шаблонов.</span><span class="sxs-lookup"><span data-stu-id="8581e-112">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="8581e-113">Получение конкретного шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="8581e-113">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="8581e-114">Получите <xref:System.Windows.Automation.AutomationElement>, шаблоны элементов управления которого вас интересуют.</span><span class="sxs-lookup"><span data-stu-id="8581e-114">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="8581e-115">Вызовите метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> или <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> для запроса определенного шаблона.</span><span class="sxs-lookup"><span data-stu-id="8581e-115">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="8581e-116">Эти методы похожи, но если шаблон не найден, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> вызывает исключение, а <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8581e-116">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8581e-117">Пример</span><span class="sxs-lookup"><span data-stu-id="8581e-117">Example</span></span>  
 <span data-ttu-id="8581e-118">В следующем примере извлекается <xref:System.Windows.Automation.AutomationElement> для элемента списка и получается <xref:System.Windows.Automation.SelectionItemPattern> из этого элемента.</span><span class="sxs-lookup"><span data-stu-id="8581e-118">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="8581e-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8581e-119">See also</span></span>

- [<span data-ttu-id="8581e-120">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="8581e-120">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
