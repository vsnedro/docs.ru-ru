---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 0d8c77d01351b0c62e0186e5aee69ca70aebe15e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274326"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="8f939-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="8f939-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>

<span data-ttu-id="8f939-103">Указанная транзакция прервана, поскольку она была незавершенной на момент закрытия сеанса и атрибуту TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute задано значение "false".</span><span class="sxs-lookup"><span data-stu-id="8f939-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8f939-104">Описание</span><span class="sxs-lookup"><span data-stu-id="8f939-104">Description</span></span>  

 <span data-ttu-id="8f939-105">Трассируется, если текущий активный сеанс был закрыт, транзакция не была завершена и TransactionAutoCompleteOnSessionClose имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8f939-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8f939-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="8f939-106">Troubleshooting</span></span>  

 <span data-ttu-id="8f939-107">Эта трассировка указывает о потенциальной ошибке в приложении, наличие которой требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="8f939-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f939-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8f939-108">See also</span></span>

- [<span data-ttu-id="8f939-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="8f939-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="8f939-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="8f939-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8f939-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="8f939-111">Administration and Diagnostics</span></span>](../index.md)
