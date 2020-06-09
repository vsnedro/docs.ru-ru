---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: f37bc252e12aef94d77c0745d36b5c8232a169eb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599741"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="6e9b8-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="6e9b8-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="6e9b8-103">Повторная попытка сообщения фиксации была отправлена участнику, который не отвечает.</span><span class="sxs-lookup"><span data-stu-id="6e9b8-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e9b8-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6e9b8-104">Description</span></span>  
 <span data-ttu-id="6e9b8-105">Трассируется, если локальному диспетчеру транзакций потребовалось заново отправить сообщение фиксации подчиненному участнику, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="6e9b8-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6e9b8-106">Диагностика</span><span class="sxs-lookup"><span data-stu-id="6e9b8-106">Troubleshooting</span></span>  
 <span data-ttu-id="6e9b8-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="6e9b8-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="6e9b8-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="6e9b8-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="6e9b8-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="6e9b8-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9b8-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="6e9b8-110">See also</span></span>

- [<span data-ttu-id="6e9b8-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6e9b8-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="6e9b8-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6e9b8-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6e9b8-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6e9b8-113">Administration and Diagnostics</span></span>](../index.md)
