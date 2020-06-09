---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 93afa0b495e20c02c58ac1fa75c31715eaa0e8dc
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596094"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="558e3-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="558e3-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="558e3-103">Скорость получения входящих сообщений слишком высока.</span><span class="sxs-lookup"><span data-stu-id="558e3-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="558e3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="558e3-104">Description</span></span>  
 <span data-ttu-id="558e3-105">Эта трассировка возникает при попытке обработки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="558e3-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="558e3-106">Не удалось перенаправить сообщение конкретному соседнему узлу, так как была превышена квота, заданная для этого узла.</span><span class="sxs-lookup"><span data-stu-id="558e3-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="558e3-107">Это происходит, если соседнему узлу, который не отвечает, не удается очистить журнал ожидания сообщений для этого узла.</span><span class="sxs-lookup"><span data-stu-id="558e3-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="558e3-108">Диагностика</span><span class="sxs-lookup"><span data-stu-id="558e3-108">Troubleshooting</span></span>  
 <span data-ttu-id="558e3-109">Необходимо снизить частоту отправки сообщений в этой сетке.</span><span class="sxs-lookup"><span data-stu-id="558e3-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558e3-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="558e3-110">See also</span></span>

- [<span data-ttu-id="558e3-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="558e3-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="558e3-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="558e3-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="558e3-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="558e3-113">Administration and Diagnostics</span></span>](../index.md)
