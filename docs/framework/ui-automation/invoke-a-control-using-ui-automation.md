---
title: Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса
description: Используйте автоматизацию пользовательского интерфейса для поиска элемента управления, соответствующего определенным условиям свойства, создайте AutomationElement, получите InvokePattern и используйте Invoke для элемента управления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: 2347a620aab848bf6bcc649a9780aa5a3a520822
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168174"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="1a2b9-103">Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1a2b9-103">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="1a2b9-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="1a2b9-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1a2b9-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="1a2b9-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="1a2b9-106">В этом примере показано выполнение следующих задач.</span><span class="sxs-lookup"><span data-stu-id="1a2b9-106">This topic demonstrates how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="1a2b9-107">Поиск элемента управления, который соответствует конкретным условиям свойств путем прохода представления элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="1a2b9-107">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
- <span data-ttu-id="1a2b9-108">Создание <xref:System.Windows.Automation.AutomationElement> для каждого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a2b9-108">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
- <span data-ttu-id="1a2b9-109">Получение объекта <xref:System.Windows.Automation.InvokePattern> из любого найденного элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , который поддерживает шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> .</span><span class="sxs-lookup"><span data-stu-id="1a2b9-109">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
- <span data-ttu-id="1a2b9-110">Использование <xref:System.Windows.Automation.InvokePattern.Invoke%2A> для вызова элемента управления из обработчика событий клиента.</span><span class="sxs-lookup"><span data-stu-id="1a2b9-110">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a2b9-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1a2b9-111">Example</span></span>  
 <span data-ttu-id="1a2b9-112">В этом примере используется метод <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> класса <xref:System.Windows.Automation.AutomationElement> для создания объекта <xref:System.Windows.Automation.InvokePattern> и вызова элемента управления с помощью метода <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a2b9-112">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="1a2b9-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1a2b9-113">See also</span></span>

- [<span data-ttu-id="1a2b9-114">Пример InvokePattern, ExpandCollapsePattern и Тогглепаттерн</span><span class="sxs-lookup"><span data-stu-id="1a2b9-114">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
