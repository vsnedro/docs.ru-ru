---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: d4fbbeaaa1daeea62b5495d0b30c37d0297ccd75
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249921"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="6ff07-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="6ff07-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>

<span data-ttu-id="6ff07-103">Скорость получения входящих сообщений слишком высока.</span><span class="sxs-lookup"><span data-stu-id="6ff07-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6ff07-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6ff07-104">Description</span></span>  

 <span data-ttu-id="6ff07-105">Эта трассировка возникает при попытке обработки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6ff07-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="6ff07-106">Не удалось перенаправить сообщение конкретному соседнему узлу, так как была превышена квота, заданная для этого узла.</span><span class="sxs-lookup"><span data-stu-id="6ff07-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="6ff07-107">Это происходит, если соседнему узлу, который не отвечает, не удается очистить журнал ожидания сообщений для этого узла.</span><span class="sxs-lookup"><span data-stu-id="6ff07-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6ff07-108">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="6ff07-108">Troubleshooting</span></span>  

 <span data-ttu-id="6ff07-109">Необходимо снизить частоту отправки сообщений в этой сетке.</span><span class="sxs-lookup"><span data-stu-id="6ff07-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff07-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6ff07-110">See also</span></span>

- [<span data-ttu-id="6ff07-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6ff07-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="6ff07-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6ff07-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6ff07-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6ff07-113">Administration and Diagnostics</span></span>](../index.md)
