---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 4b016f53a75d9527a5cd1bbadacacd650b7f35b0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601923"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="0b5e6-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="0b5e6-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="0b5e6-103">Сообщение удалено из очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0b5e6-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0b5e6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0b5e6-104">Description</span></span>  
 <span data-ttu-id="0b5e6-105">Данная трассировка указывает, что сообщение MSMQ было удалено.</span><span class="sxs-lookup"><span data-stu-id="0b5e6-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="0b5e6-106">Сообщения MSMQ могут быть удалены, когда Windows Communication Foundation (WCF) (используется с NetMsmqBinding или MsmqIntegrationBinding) не может их обработать.</span><span class="sxs-lookup"><span data-stu-id="0b5e6-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="0b5e6-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="0b5e6-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="0b5e6-108">Подозрительное сообщение отбрасывается, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.</span><span class="sxs-lookup"><span data-stu-id="0b5e6-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="0b5e6-109">Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.</span><span class="sxs-lookup"><span data-stu-id="0b5e6-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="0b5e6-110">Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="0b5e6-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b5e6-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="0b5e6-111">See also</span></span>

- [<span data-ttu-id="0b5e6-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0b5e6-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="0b5e6-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0b5e6-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0b5e6-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0b5e6-114">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="0b5e6-115">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="0b5e6-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
