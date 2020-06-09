---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 162452d5d12859571d78ef19cf1d838953ee7acd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596211"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="e8ea1-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="e8ea1-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="e8ea1-103">Координатору, который не отвечает, было повторно отправлено сообщение Replay.</span><span class="sxs-lookup"><span data-stu-id="e8ea1-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e8ea1-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e8ea1-104">Description</span></span>  
 <span data-ttu-id="e8ea1-105">Трассируется, если локальному диспетчеру транзакций потребовалось повторно отправить сообщение Replay вышестоящему координатору, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="e8ea1-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e8ea1-106">Диагностика</span><span class="sxs-lookup"><span data-stu-id="e8ea1-106">Troubleshooting</span></span>  
 <span data-ttu-id="e8ea1-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="e8ea1-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="e8ea1-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="e8ea1-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="e8ea1-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="e8ea1-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ea1-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e8ea1-110">See also</span></span>

- [<span data-ttu-id="e8ea1-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="e8ea1-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="e8ea1-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="e8ea1-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e8ea1-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="e8ea1-113">Administration and Diagnostics</span></span>](../index.md)
