---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 69da35f65e04a3cba15885c4fe6e57d63762cb1c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260348"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="1f122-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="1f122-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>

<span data-ttu-id="1f122-103">Подозрительное сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="1f122-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1f122-104">Описание</span><span class="sxs-lookup"><span data-stu-id="1f122-104">Description</span></span>  

 <span data-ttu-id="1f122-105">Указывает, что было обнаружено и отклонено подозрительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="1f122-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="1f122-106">Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="1f122-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="1f122-107">Отклоненное сообщение отправляется обратно в [очередь недоставленных](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)сообщений отправителя.</span><span class="sxs-lookup"><span data-stu-id="1f122-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="1f122-108">Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="1f122-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="1f122-109">Дополнительные сведения о том, что означает отклоненное сообщение в MSMQ, см. в разделе [мкмаркмессажережектед](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="1f122-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f122-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1f122-110">See also</span></span>

- [<span data-ttu-id="1f122-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="1f122-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="1f122-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="1f122-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1f122-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="1f122-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="1f122-114">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="1f122-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="1f122-115">[мкмаркмессажережектед](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="1f122-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
