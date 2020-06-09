---
title: Correlation
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: e7ccb58b11003638e15bdbc7b7aa326abbac1b71
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579713"
---
# <a name="correlation"></a><span data-ttu-id="10979-102">Correlation</span><span class="sxs-lookup"><span data-stu-id="10979-102">Correlation</span></span>
<span data-ttu-id="10979-103">При взаимодействии приложения службы рабочего процесса с другими службами важно обеспечить передачу сообщений соответствующему экземпляру рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="10979-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="10979-104">Механизм для этого предоставляет корреляция.</span><span class="sxs-lookup"><span data-stu-id="10979-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="10979-105">В подразделах этого раздела приведены общие сведения о корреляции, порядке ее использования в различных сценариях служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="10979-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10979-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="10979-106">In This Section</span></span>  
 [<span data-ttu-id="10979-107">Общие сведения о корреляции</span><span class="sxs-lookup"><span data-stu-id="10979-107">Correlation Overview</span></span>](correlation-overview.md)  
 <span data-ttu-id="10979-108">Содержит общие сведения о типах корреляции, доступных в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10979-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="10979-109">Сохраняемый дуплекс</span><span class="sxs-lookup"><span data-stu-id="10979-109">Durable Duplex</span></span>](durable-duplex-correlation.md)  
 <span data-ttu-id="10979-110">Описывает сохраняемую дуплексную корреляцию.</span><span class="sxs-lookup"><span data-stu-id="10979-110">Describes durable duplex correlation.</span></span>
  
 [<span data-ttu-id="10979-111">Запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="10979-111">Request-Reply</span></span>](request-reply-correlation.md)  
 <span data-ttu-id="10979-112">Описывает корреляцию запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="10979-112">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="10979-113">Устранение неполадок корреляции</span><span class="sxs-lookup"><span data-stu-id="10979-113">Troubleshooting Correlation</span></span>](troubleshooting-correlation.md)  
 <span data-ttu-id="10979-114">Предоставляет методы для устранения неполадок корреляции.</span><span class="sxs-lookup"><span data-stu-id="10979-114">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10979-115">См. также</span><span class="sxs-lookup"><span data-stu-id="10979-115">See also</span></span>

- <xref:System.ServiceModel.Activities.CorrelationHandle>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.Receive>
- <xref:System.ServiceModel.CorrelationQuery>
