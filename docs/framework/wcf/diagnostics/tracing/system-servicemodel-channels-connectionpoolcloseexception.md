---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286959"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="e0429-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="e0429-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>

<span data-ttu-id="e0429-103">При закрытии подключений в этом пуле подключений возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="e0429-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e0429-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e0429-104">Description</span></span>  

 <span data-ttu-id="e0429-105">Эта трассировка уровня ошибок указывает на то, что при закрытии пулов соединений, используемых компонентом пулов соединений Windows Communication Foundation (WCF), произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="e0429-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="e0429-106">Эта ошибка может быть вызвана тем, что не удалось закрыть подключение (или набор подключений) из пула в течение времени ожидания (CloseTimeout).</span><span class="sxs-lookup"><span data-stu-id="e0429-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="e0429-107">При выдаче этого исключения все оставшиеся незакрытые подключения из этого пула прерываются. Незакрытые подключения из других пулов оставляются.</span><span class="sxs-lookup"><span data-stu-id="e0429-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0429-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e0429-108">See also</span></span>

- [<span data-ttu-id="e0429-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="e0429-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="e0429-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="e0429-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e0429-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="e0429-111">Administration and Diagnostics</span></span>](../index.md)
