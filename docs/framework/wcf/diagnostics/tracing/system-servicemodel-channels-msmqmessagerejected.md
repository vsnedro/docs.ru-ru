---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 12978af11ac3663403deaeb21818643ca2d366aa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260361"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="0138a-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="0138a-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>

<span data-ttu-id="0138a-103">MSMQ отклонила сообщение.</span><span class="sxs-lookup"><span data-stu-id="0138a-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0138a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0138a-104">Description</span></span>  

 <span data-ttu-id="0138a-105">Данная трассировка показывает, что сообщение MSMQ было отклонено. </span><span class="sxs-lookup"><span data-stu-id="0138a-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="0138a-106">Сообщения MSMQ могут быть отклонены, если Windows Communication Foundation (WCF) (используется с NetMsmqBinding или MsmqIntegrationBinding) не может их обработать.</span><span class="sxs-lookup"><span data-stu-id="0138a-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="0138a-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="0138a-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="0138a-108">Подозрительное сообщение отклоняется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="0138a-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="0138a-109">Отклоненное сообщение отправляется обратно в [очередь недоставленных](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)сообщений отправителя.</span><span class="sxs-lookup"><span data-stu-id="0138a-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="0138a-110">Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="0138a-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="0138a-111">Дополнительные сведения о том, что означает отклоненное сообщение в MSMQ, см. в разделе [мкмаркмессажережектед](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="0138a-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0138a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0138a-112">See also</span></span>

- [<span data-ttu-id="0138a-113">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0138a-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="0138a-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0138a-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0138a-115">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0138a-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="0138a-116">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="0138a-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="0138a-117">[мкмаркмессажережектед](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0138a-117">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
