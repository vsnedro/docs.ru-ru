---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598155"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="e157c-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="e157c-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="e157c-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="e157c-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="e157c-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e157c-104">Description</span></span>  
 <span data-ttu-id="e157c-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="e157c-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="e157c-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="e157c-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="e157c-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="e157c-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="e157c-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="e157c-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="e157c-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="e157c-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e157c-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e157c-110">See also</span></span>

- [<span data-ttu-id="e157c-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="e157c-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="e157c-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="e157c-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e157c-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="e157c-113">Administration and Diagnostics</span></span>](../index.md)
