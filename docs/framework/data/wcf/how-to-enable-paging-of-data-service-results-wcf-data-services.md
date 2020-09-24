---
title: Практическое руководство. Включение разбивки на страницы результатов службы данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 1c8bb8fe757c35f6096b139da6ca939b1ce1c283
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150626"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="b1401-102">Практическое руководство. Включение разбивки на страницы результатов службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="b1401-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>

<span data-ttu-id="b1401-103">WCF Data Services позволяет ограничить количество сущностей, возвращаемых запросом службы данных.</span><span class="sxs-lookup"><span data-stu-id="b1401-103">WCF Data Services enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="b1401-104">Пределы разбиения на страницы определены в методе, который вызывается при инициализации службы, и могут устанавливаться отдельно для каждого набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="b1401-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="b1401-105">Если включена подкачка страниц, то последняя запись в канале содержит ссылку на следующую страницу данных.</span><span class="sxs-lookup"><span data-stu-id="b1401-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="b1401-106">Дополнительные сведения см. [в разделе Настройка службы данных](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b1401-106">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="b1401-107">В этом разделе показывается, как изменить службу данных, чтобы включить разбиение на страницы возвращаемых `Customers` и наборов сущностей `Orders`.</span><span class="sxs-lookup"><span data-stu-id="b1401-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="b1401-108">В примере этого раздела используется образец службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="b1401-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="b1401-109">Эта служба создается при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b1401-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="b1401-110">Как включить разбиение на страницы возвращаемых клиентов и наборов сущностей Orders</span><span class="sxs-lookup"><span data-stu-id="b1401-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
- <span data-ttu-id="b1401-111">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="b1401-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="b1401-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b1401-112">See also</span></span>

- [<span data-ttu-id="b1401-113">Загрузка отложенного содержимого</span><span class="sxs-lookup"><span data-stu-id="b1401-113">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="b1401-114">Практическое руководство. Загрузка результатов, разбитых на страницы</span><span class="sxs-lookup"><span data-stu-id="b1401-114">How to: Load Paged Results</span></span>](how-to-load-paged-results-wcf-data-services.md)
