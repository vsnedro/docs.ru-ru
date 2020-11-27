---
title: Корреляция
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: 1a357dd9469d7428af56772d3241e59766429990
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286777"
---
# <a name="correlation"></a><span data-ttu-id="96083-102">Корреляция</span><span class="sxs-lookup"><span data-stu-id="96083-102">Correlation</span></span>

<span data-ttu-id="96083-103">При взаимодействии приложения службы рабочего процесса с другими службами важно обеспечить передачу сообщений соответствующему экземпляру рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="96083-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="96083-104">Механизм для этого предоставляет корреляция.</span><span class="sxs-lookup"><span data-stu-id="96083-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="96083-105">В подразделах этого раздела приведены общие сведения о корреляции, порядке ее использования в различных сценариях служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="96083-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96083-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="96083-106">In This Section</span></span>  

 [<span data-ttu-id="96083-107">Общие сведения о корреляции</span><span class="sxs-lookup"><span data-stu-id="96083-107">Correlation Overview</span></span>](correlation-overview.md)  
 <span data-ttu-id="96083-108">Содержит общие сведения о типах корреляции, доступных в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96083-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="96083-109">Сохраняемый дуплекс</span><span class="sxs-lookup"><span data-stu-id="96083-109">Durable Duplex</span></span>](durable-duplex-correlation.md)  
 <span data-ttu-id="96083-110">Описывает сохраняемую дуплексную корреляцию.</span><span class="sxs-lookup"><span data-stu-id="96083-110">Describes durable duplex correlation.</span></span>
  
 [<span data-ttu-id="96083-111">Запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="96083-111">Request-Reply</span></span>](request-reply-correlation.md)  
 <span data-ttu-id="96083-112">Описывает корреляцию запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="96083-112">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="96083-113">Устранение неполадок корреляции</span><span class="sxs-lookup"><span data-stu-id="96083-113">Troubleshooting Correlation</span></span>](troubleshooting-correlation.md)  
 <span data-ttu-id="96083-114">Предоставляет методы для устранения неполадок корреляции.</span><span class="sxs-lookup"><span data-stu-id="96083-114">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96083-115">См. также</span><span class="sxs-lookup"><span data-stu-id="96083-115">See also</span></span>

- <xref:System.ServiceModel.Activities.CorrelationHandle>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.Receive>
- <xref:System.ServiceModel.CorrelationQuery>
