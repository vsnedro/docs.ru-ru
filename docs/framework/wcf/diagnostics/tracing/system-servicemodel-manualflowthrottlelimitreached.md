---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: bffa6361df5a50748f45aa3004f7a307ad516d7b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580493"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="d3962-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d3962-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="d3962-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d3962-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="d3962-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d3962-104">Description</span></span>  
 <span data-ttu-id="d3962-105">Система достигла предела, заданного ограничителем ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="d3962-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="d3962-106">Значение регулировки, в зависимости от конкретного случая, может быть изменено с помощью изменения свойства ManualFlowControlLimit либо в классе ServiceHost, либо в классе InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="d3962-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="d3962-107">Такая трассировка выдается, если ручной предел управления потоками первоначально снижается до 0.</span><span class="sxs-lookup"><span data-stu-id="d3962-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="d3962-108">Последующие изменения до 0 не трассируются.</span><span class="sxs-lookup"><span data-stu-id="d3962-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="d3962-109">Предел управления потоками в контексте экземпляра трассируется один раз для каждого контекста.</span><span class="sxs-lookup"><span data-stu-id="d3962-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3962-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="d3962-110">See also</span></span>

- [<span data-ttu-id="d3962-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="d3962-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="d3962-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="d3962-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d3962-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="d3962-113">Administration and Diagnostics</span></span>](../index.md)
