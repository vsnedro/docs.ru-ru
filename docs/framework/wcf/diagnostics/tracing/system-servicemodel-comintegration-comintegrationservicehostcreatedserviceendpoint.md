---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: aeeba38eaf674453f4c87cf62f5088c55b5fde2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290820"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="b64b2-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="b64b2-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>

<span data-ttu-id="b64b2-103">Не удается переместить или удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="b64b2-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b64b2-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b64b2-104">Description</span></span>  

 <span data-ttu-id="b64b2-105">Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="b64b2-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="b64b2-106">Сообщения MSMQ используются Windows Communication Foundation (WCF) (при использовании с NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка связана с выбранным значением свойства в `ReceiveErrorHandling` NetMsmqBinding или MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="b64b2-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="b64b2-107">Эта трассировка не указывает на общий сбой системы.</span><span class="sxs-lookup"><span data-stu-id="b64b2-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="b64b2-108">Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения.</span><span class="sxs-lookup"><span data-stu-id="b64b2-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="b64b2-109">Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="b64b2-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64b2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b64b2-110">See also</span></span>

- [<span data-ttu-id="b64b2-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b64b2-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="b64b2-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="b64b2-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b64b2-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="b64b2-113">Administration and Diagnostics</span></span>](../index.md)
