---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 8b81cdcaf74aca044260495867b2c4f1de517682
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593754"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="2e09a-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="2e09a-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="2e09a-103">Не удается переместить или удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="2e09a-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e09a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="2e09a-104">Description</span></span>  
 <span data-ttu-id="2e09a-105">Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="2e09a-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="2e09a-106">Сообщения MSMQ используются Windows Communication Foundation (WCF) (при использовании с NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка связана с выбранным значением свойства в `ReceiveErrorHandling` NetMsmqBinding или MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="2e09a-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="2e09a-107">Эта трассировка не указывает на общий сбой системы.</span><span class="sxs-lookup"><span data-stu-id="2e09a-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="2e09a-108">Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения.</span><span class="sxs-lookup"><span data-stu-id="2e09a-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="2e09a-109">Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="2e09a-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e09a-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e09a-110">See also</span></span>

- [<span data-ttu-id="2e09a-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2e09a-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="2e09a-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="2e09a-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2e09a-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="2e09a-113">Administration and Diagnostics</span></span>](../index.md)
