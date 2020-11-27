---
title: Вызов событий из поставщика автоматизации пользовательского интерфейса
description: См. пример, показывающий, как вызвать событие из поставщика автоматизации пользовательского интерфейса. Он вызывает событие автоматизации пользовательского интерфейса в реализации пользовательского элемента управления "Кнопка".
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 73be7fd92f3fde90255326c51bed03427fd68e8d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250493"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="9d86b-104">Вызов событий из поставщика автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9d86b-104">Raise Events from a UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="9d86b-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="9d86b-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9d86b-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="9d86b-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="9d86b-107">В этом разделе содержится пример кода, демонстрирующий вызов события из поставщика автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9d86b-107">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d86b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9d86b-108">Example</span></span>  

 <span data-ttu-id="9d86b-109">В следующем примере событие [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] вызывается в реализации пользовательского элемента управления "Кнопка".</span><span class="sxs-lookup"><span data-stu-id="9d86b-109">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="9d86b-110">Эта реализация позволяет клиентскому приложению модели автоматизации пользовательского интерфейса имитировать нажатие кнопки.</span><span class="sxs-lookup"><span data-stu-id="9d86b-110">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="9d86b-111">Для исключения излишней обработки в этом примере проверяется <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> , чтобы увидеть, должны ли вызываться события.</span><span class="sxs-lookup"><span data-stu-id="9d86b-111">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="9d86b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9d86b-112">See also</span></span>

- [<span data-ttu-id="9d86b-113">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9d86b-113">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
