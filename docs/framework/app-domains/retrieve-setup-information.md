---
title: Извлечение сведений о настройке из домена приложения
description: Извлечение сведений о настройке из домена приложения в .NET с использованием класса System.AppDomain или объекта AppDomainSetup.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
ms.openlocfilehash: 3b7fdd302ac11caa423815483a4add38264f0910
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325659"
---
# <a name="retrieve-setup-information-from-an-application-domain"></a><span data-ttu-id="ffe6c-103">Извлечение сведений о настройке из домена приложения</span><span class="sxs-lookup"><span data-stu-id="ffe6c-103">Retrieve setup information from an application domain</span></span>

<span data-ttu-id="ffe6c-104">Каждый экземпляр домена приложения содержит свойства и сведения <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-104">Each instance of an application domain consists of both properties and <xref:System.AppDomainSetup> information.</span></span> <span data-ttu-id="ffe6c-105">Сведения о настройке можно получить из домена приложения с помощью класса <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-105">You can retrieve setup information from an application domain using the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="ffe6c-106">Этот класс предоставляет несколько членов, извлекающих сведения конфигурации домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-106">This class provides several members that retrieve configuration information about an application domain.</span></span>  
  
 <span data-ttu-id="ffe6c-107">Кроме того, для получения сведений о настройке домена приложения можно выполнить запрос объекта **AppDomainSetup**, который был передан в домен при его создании.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-107">You can also query the **AppDomainSetup** object for the application domain to obtain setup information that was passed to the domain when it was created.</span></span>  
  
 <span data-ttu-id="ffe6c-108">В следующем примере создается домен приложения и выполняется вывод значений нескольких его членов на консоль.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-108">The following example creates a new application domain and then prints several member values to the console.</span></span>  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 <span data-ttu-id="ffe6c-109">В следующем примере для домена приложения задаются и извлекаются сведения о настройке.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-109">The following example sets, and then retrieves, setup information for an application domain.</span></span> <span data-ttu-id="ffe6c-110">`AppDomain.SetupInformation.ApplicationBase` считывает информацию о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ffe6c-110">`AppDomain.SetupInformation.ApplicationBase` gets the configuration information.</span></span>  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ffe6c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ffe6c-111">See also</span></span>

- [<span data-ttu-id="ffe6c-112">Программирование с использованием доменов приложений</span><span class="sxs-lookup"><span data-stu-id="ffe6c-112">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="ffe6c-113">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="ffe6c-113">Using Application Domains</span></span>](use.md)
