---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: dd2a0b67ec140aa2e6fe1abad8e85c0206abd8ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579025"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="08bee-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="08bee-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="08bee-103">Истекло время ожидания службой протокола WS-AT ответа на результативное сообщение от неустойчивого участника.</span><span class="sxs-lookup"><span data-stu-id="08bee-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="08bee-104">При возвращении участника результат транзакции будет поставлен под сомнение.</span><span class="sxs-lookup"><span data-stu-id="08bee-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="08bee-105">Описание</span><span class="sxs-lookup"><span data-stu-id="08bee-105">Description</span></span>  
 <span data-ttu-id="08bee-106">Трассируется, когда неустойчивый участник принял решение зафиксировать или прервать транзакцию, однако не ответил на сообщение Commit или Rollback в течение заданного времени.</span><span class="sxs-lookup"><span data-stu-id="08bee-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="08bee-107">Диагностика</span><span class="sxs-lookup"><span data-stu-id="08bee-107">Troubleshooting</span></span>  
 <span data-ttu-id="08bee-108">Убедитесь, что все неустойчивые участники имеют возможность ответить в течение заданного времени.</span><span class="sxs-lookup"><span data-stu-id="08bee-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="08bee-109">Период времени по умолчанию - 180 секунд.</span><span class="sxs-lookup"><span data-stu-id="08bee-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="08bee-110">Если этого недостаточно, увеличьте значение политики таймера `VolatileOutcomeDelay` для протокола WS-AT.</span><span class="sxs-lookup"><span data-stu-id="08bee-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bee-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="08bee-111">See also</span></span>

- [<span data-ttu-id="08bee-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="08bee-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="08bee-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="08bee-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="08bee-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="08bee-114">Administration and Diagnostics</span></span>](../index.md)
