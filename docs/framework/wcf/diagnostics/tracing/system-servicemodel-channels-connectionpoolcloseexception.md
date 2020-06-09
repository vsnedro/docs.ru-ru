---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 0a312d192546655dc327667c00f4f2bbc0c15fdb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602054"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="3d05a-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="3d05a-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="3d05a-103">При закрытии подключений в этом пуле подключений возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="3d05a-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3d05a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="3d05a-104">Description</span></span>  
 <span data-ttu-id="3d05a-105">Эта трассировка уровня ошибок указывает на то, что при закрытии пулов соединений, используемых компонентом пулов соединений Windows Communication Foundation (WCF), произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="3d05a-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="3d05a-106">Эта ошибка может быть вызвана тем, что не удалось закрыть подключение (или набор подключений) из пула в течение времени ожидания (CloseTimeout).</span><span class="sxs-lookup"><span data-stu-id="3d05a-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="3d05a-107">При выдаче этого исключения все оставшиеся незакрытые подключения из этого пула прерываются. Незакрытые подключения из других пулов оставляются.</span><span class="sxs-lookup"><span data-stu-id="3d05a-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d05a-108">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3d05a-108">See also</span></span>

- [<span data-ttu-id="3d05a-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="3d05a-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="3d05a-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="3d05a-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3d05a-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="3d05a-111">Administration and Diagnostics</span></span>](../index.md)
