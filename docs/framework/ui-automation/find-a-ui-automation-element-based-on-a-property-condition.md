---
title: Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
description: Найти элемент модели автоматизации пользовательского интерфейса на основе условия для свойства. Нахождение элемента в дереве автоматизации пользовательского интерфейса на основе определенного свойства или свойств.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 112f38d6bef726f92dbf13da70b88732929175dd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557688"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="2dd5d-104">Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства</span><span class="sxs-lookup"><span data-stu-id="2dd5d-104">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="2dd5d-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="2dd5d-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2dd5d-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="2dd5d-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2dd5d-107">В этом разделе содержится пример кода, в котором показано, как можно наыскать элемент в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дереве на основе конкретного свойства или свойств.</span><span class="sxs-lookup"><span data-stu-id="2dd5d-107">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dd5d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2dd5d-108">Example</span></span>  
 <span data-ttu-id="2dd5d-109">В следующем примере задается набор условий свойства, которые определяют определенный элемент (или элементы), представляющие интерес в <xref:System.Windows.Automation.AutomationElement> дереве.</span><span class="sxs-lookup"><span data-stu-id="2dd5d-109">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="2dd5d-110">Затем выполняется поиск всех соответствующих элементов с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метода, включающего ряд <xref:System.Windows.Automation.AndCondition> логических операций для ограничения количества совпадающих элементов.</span><span class="sxs-lookup"><span data-stu-id="2dd5d-110">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2dd5d-111">При поиске из необходимо <xref:System.Windows.Automation.AutomationElement.RootElement%2A> попытаться получить только прямые дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="2dd5d-111">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="2dd5d-112">Поиск потомков может осуществлять итерацию сотен или даже тысяч элементов, что может привести к переполнению стека.</span><span class="sxs-lookup"><span data-stu-id="2dd5d-112">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="2dd5d-113">Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.</span><span class="sxs-lookup"><span data-stu-id="2dd5d-113">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="2dd5d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2dd5d-114">See also</span></span>

- <span data-ttu-id="2dd5d-115">[Пример пункта меню InvokePattern и ExpandCollapsePattern](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2dd5d-115">[InvokePattern and ExpandCollapsePattern Menu Item Sample](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="2dd5d-116">Получение элементов автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2dd5d-116">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="2dd5d-117">Использование свойства AutomationID</span><span class="sxs-lookup"><span data-stu-id="2dd5d-117">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
