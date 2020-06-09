---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: 8371dba79573f480b264ed6185b8cf0098e3cb2a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576581"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="5d665-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="5d665-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="5d665-103">Заданная транзакция для заданной операции завершена в результате асинхронного прерывания.</span><span class="sxs-lookup"><span data-stu-id="5d665-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5d665-104">Описание</span><span class="sxs-lookup"><span data-stu-id="5d665-104">Description</span></span>  
 <span data-ttu-id="5d665-105">Текущая транзакция была прервана, потому что другой участник спровоцировал прерывание, истекло время ожидания или из-за внутренней ошибки участника транзакции.</span><span class="sxs-lookup"><span data-stu-id="5d665-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="5d665-106">Диагностика</span><span class="sxs-lookup"><span data-stu-id="5d665-106">Troubleshooting</span></span>  
 <span data-ttu-id="5d665-107">Если это прерывание произошло неожиданно, проверьте системные журналы, чтобы определить истинную причину прерывания.</span><span class="sxs-lookup"><span data-stu-id="5d665-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d665-108">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="5d665-108">See also</span></span>

- [<span data-ttu-id="5d665-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="5d665-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="5d665-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="5d665-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5d665-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="5d665-111">Administration and Diagnostics</span></span>](../index.md)
