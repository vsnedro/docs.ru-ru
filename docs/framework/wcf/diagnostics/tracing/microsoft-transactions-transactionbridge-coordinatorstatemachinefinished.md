---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 2d874cebe96b9caa99032e2881e19ec9cd34d047
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259015"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="0a766-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="0a766-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>

<span data-ttu-id="0a766-103">Конечный автомат для перечисления координаторов перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="0a766-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0a766-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0a766-104">Description</span></span>  

 <span data-ttu-id="0a766-105">Регистрируется, если локальный диспетчер транзакция полагает, что перечисление координаторов более высокого уровня завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="0a766-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="0a766-106">Результатом перечисления может быть значение Committed, Aborted или Forgotten.</span><span class="sxs-lookup"><span data-stu-id="0a766-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="0a766-107">Кроме того, это событие регистрируется, если на этапе подготовки локальный диспетчер транзакций голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="0a766-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a766-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0a766-108">See also</span></span>

- [<span data-ttu-id="0a766-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0a766-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="0a766-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0a766-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0a766-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0a766-111">Administration and Diagnostics</span></span>](../index.md)
