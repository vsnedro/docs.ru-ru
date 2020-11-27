---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6e8b134f61d2dc9bd5daf541db4ec81604166baa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260387"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="6ad13-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="6ad13-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>

<span data-ttu-id="6ad13-103">Сообщение удалено из очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6ad13-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6ad13-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6ad13-104">Description</span></span>  

 <span data-ttu-id="6ad13-105">Данная трассировка указывает, что сообщение MSMQ было удалено.</span><span class="sxs-lookup"><span data-stu-id="6ad13-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="6ad13-106">Сообщения MSMQ могут быть удалены, когда Windows Communication Foundation (WCF) (используется с NetMsmqBinding или MsmqIntegrationBinding) не может их обработать.</span><span class="sxs-lookup"><span data-stu-id="6ad13-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="6ad13-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="6ad13-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="6ad13-108">Подозрительное сообщение отбрасывается, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.</span><span class="sxs-lookup"><span data-stu-id="6ad13-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="6ad13-109">Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.</span><span class="sxs-lookup"><span data-stu-id="6ad13-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="6ad13-110">Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="6ad13-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad13-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6ad13-111">See also</span></span>

- [<span data-ttu-id="6ad13-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6ad13-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="6ad13-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6ad13-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6ad13-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6ad13-114">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="6ad13-115">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="6ad13-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
