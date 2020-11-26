---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235120"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="11384-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="11384-102">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="11384-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="11384-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="11384-104">Описание</span><span class="sxs-lookup"><span data-stu-id="11384-104">Description</span></span>  

 <span data-ttu-id="11384-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="11384-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="11384-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="11384-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="11384-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="11384-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="11384-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="11384-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="11384-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="11384-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11384-110">См. также</span><span class="sxs-lookup"><span data-stu-id="11384-110">See also</span></span>

- [<span data-ttu-id="11384-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="11384-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="11384-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="11384-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="11384-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="11384-113">Administration and Diagnostics</span></span>](../index.md)
