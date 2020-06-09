---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 0652b3b76c155431b68c5ee0dc8f83977f9845a5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594365"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="21b0f-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="21b0f-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="21b0f-103">Конечный автомат для перечисления участников перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="21b0f-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="21b0f-104">Описание</span><span class="sxs-lookup"><span data-stu-id="21b0f-104">Description</span></span>  
 <span data-ttu-id="21b0f-105">Трассируется, когда перечисление подчиненных участников завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="21b0f-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="21b0f-106">Результатом для перечисления может быть значение Committed или Aborted.</span><span class="sxs-lookup"><span data-stu-id="21b0f-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="21b0f-107">Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="21b0f-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b0f-108">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="21b0f-108">See also</span></span>

- [<span data-ttu-id="21b0f-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="21b0f-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="21b0f-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="21b0f-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="21b0f-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="21b0f-111">Administration and Diagnostics</span></span>](../index.md)
