---
title: Реализация поставщиков UI Automation в в приложении клиента
description: См. Пример реализации поставщика автоматизации пользовательского интерфейса на стороне клиента в приложении. Обратите внимание, что это редкий сценарий.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: 486e05f9080b686c48454dfcfceaaa666fa57f67
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269591"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="5a49f-104">Реализация поставщиков UI Automation в в приложении клиента</span><span class="sxs-lookup"><span data-stu-id="5a49f-104">Implement UI Automation Providers in a Client Application</span></span>

> [!NOTE]
> <span data-ttu-id="5a49f-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="5a49f-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5a49f-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="5a49f-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="5a49f-107">В этом разделе содержится пример кода, демонстрирующий реализацию клиентского поставщика автоматизации пользовательского интерфейса в приложении.</span><span class="sxs-lookup"><span data-stu-id="5a49f-107">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="5a49f-108">Это происходит редко.</span><span class="sxs-lookup"><span data-stu-id="5a49f-108">This is an uncommon scenario.</span></span> <span data-ttu-id="5a49f-109">Чаще всего клиентское приложение автоматизации пользовательского интерфейса использует поставщики на стороне сервера или поставщики на стороне клиента, которые находятся в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="5a49f-109">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a49f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5a49f-110">Example</span></span>  

 <span data-ttu-id="5a49f-111">В следующем примере кода реализуется простой поставщик для окна консоли.</span><span class="sxs-lookup"><span data-stu-id="5a49f-111">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="5a49f-112">Этот код не имеет никаких полезных функциональных возможностей, но он предназначен для демонстрации основных действий по настройке поставщика в коде клиента и его регистрации с помощью метода <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a49f-112">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="5a49f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5a49f-113">See also</span></span>

- [<span data-ttu-id="5a49f-114">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5a49f-114">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="5a49f-115">Регистрация сборки поставщика на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="5a49f-115">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="5a49f-116">Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="5a49f-116">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="5a49f-117">Реализация клиентского поставщика автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5a49f-117">Client-Side UI Automation Provider Implementation</span></span>](client-side-ui-automation-provider-implementation.md)
