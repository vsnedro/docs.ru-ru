---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 3b9a3703e49c3932f62fcfb6994c9028b074bbe8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594417"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="c6363-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="c6363-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="c6363-103">Конечный автомат для перечисления координаторов перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="c6363-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c6363-104">Описание</span><span class="sxs-lookup"><span data-stu-id="c6363-104">Description</span></span>  
 <span data-ttu-id="c6363-105">Регистрируется, если локальный диспетчер транзакция полагает, что перечисление координаторов более высокого уровня завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="c6363-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="c6363-106">Результатом перечисления может быть значение Committed, Aborted или Forgotten.</span><span class="sxs-lookup"><span data-stu-id="c6363-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="c6363-107">Кроме того, это событие регистрируется, если на этапе подготовки локальный диспетчер транзакций голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="c6363-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6363-108">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c6363-108">See also</span></span>

- [<span data-ttu-id="c6363-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="c6363-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="c6363-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="c6363-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c6363-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="c6363-111">Administration and Diagnostics</span></span>](../index.md)
