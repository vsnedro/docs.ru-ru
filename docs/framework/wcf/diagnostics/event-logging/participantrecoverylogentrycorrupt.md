---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 8fe65199425196ab8910d9ffc9f70d7224137825
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278574"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="86845-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="86845-102">ParticipantRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="86845-103">Идентификатор: 138</span><span class="sxs-lookup"><span data-stu-id="86845-103">Id: 138</span></span>  
  
 <span data-ttu-id="86845-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="86845-104">Severity: Error</span></span>  
  
 <span data-ttu-id="86845-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="86845-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="86845-106">Описание</span><span class="sxs-lookup"><span data-stu-id="86845-106">Description</span></span>  

 <span data-ttu-id="86845-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="86845-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="86845-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="86845-108">Data loss may result from this error.</span></span> <span data-ttu-id="86845-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="86845-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86845-110">См. также</span><span class="sxs-lookup"><span data-stu-id="86845-110">See also</span></span>

- [<span data-ttu-id="86845-111">Ведение журналов событий</span><span class="sxs-lookup"><span data-stu-id="86845-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="86845-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="86845-112">Events General Reference</span></span>](events-general-reference.md)
