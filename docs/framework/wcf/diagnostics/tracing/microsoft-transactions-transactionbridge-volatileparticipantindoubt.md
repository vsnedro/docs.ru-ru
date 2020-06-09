---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: ab1c2c8afe3a66536810a614cc6deac12519cb9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599637"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="ec66c-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="ec66c-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="ec66c-103">Служба протокола WS-AT получила сообщение "Готово" или "Повторная отправка" от неопознанного неустойчивого участника.</span><span class="sxs-lookup"><span data-stu-id="ec66c-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="ec66c-104">Ошибка, возвращенная участнику, оповещает о том, что результат транзакции не известен.</span><span class="sxs-lookup"><span data-stu-id="ec66c-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec66c-105">Описание</span><span class="sxs-lookup"><span data-stu-id="ec66c-105">Description</span></span>  
 <span data-ttu-id="ec66c-106">Трассируется, когда локальный диспетчер транзакций получает сообщение "Готово" или "Повторная отправка" от уже забытого неустойчивого перечисления.</span><span class="sxs-lookup"><span data-stu-id="ec66c-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ec66c-107">Диагностика</span><span class="sxs-lookup"><span data-stu-id="ec66c-107">Troubleshooting</span></span>  
 <span data-ttu-id="ec66c-108">Выявите возможные причины поздних сообщений, поступающих от неустойчивого участника.</span><span class="sxs-lookup"><span data-stu-id="ec66c-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec66c-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ec66c-109">See also</span></span>

- [<span data-ttu-id="ec66c-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ec66c-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="ec66c-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ec66c-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ec66c-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ec66c-112">Administration and Diagnostics</span></span>](../index.md)
