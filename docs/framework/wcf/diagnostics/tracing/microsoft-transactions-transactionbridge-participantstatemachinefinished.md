---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: bd6c9124e6346437e2bb35df620e00bad13b60f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258950"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="59667-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="59667-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>

<span data-ttu-id="59667-103">Конечный автомат для перечисления участников перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="59667-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="59667-104">Описание</span><span class="sxs-lookup"><span data-stu-id="59667-104">Description</span></span>  

 <span data-ttu-id="59667-105">Трассируется, когда перечисление подчиненных участников завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="59667-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="59667-106">Результатом для перечисления может быть значение Committed или Aborted.</span><span class="sxs-lookup"><span data-stu-id="59667-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="59667-107">Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="59667-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59667-108">См. также</span><span class="sxs-lookup"><span data-stu-id="59667-108">See also</span></span>

- [<span data-ttu-id="59667-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="59667-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="59667-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="59667-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="59667-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="59667-111">Administration and Diagnostics</span></span>](../index.md)
