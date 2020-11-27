---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295368"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="41ad4-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="41ad4-102">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="41ad4-103">Идентификатор: 139</span><span class="sxs-lookup"><span data-stu-id="41ad4-103">Id: 139</span></span>  
  
 <span data-ttu-id="41ad4-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="41ad4-104">Severity: Error</span></span>  
  
 <span data-ttu-id="41ad4-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="41ad4-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="41ad4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="41ad4-106">Description</span></span>  

 <span data-ttu-id="41ad4-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="41ad4-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="41ad4-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="41ad4-108">Data loss may result from this error.</span></span> <span data-ttu-id="41ad4-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="41ad4-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ad4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="41ad4-110">See also</span></span>

- [<span data-ttu-id="41ad4-111">Ведение журналов событий</span><span class="sxs-lookup"><span data-stu-id="41ad4-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="41ad4-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="41ad4-112">Events General Reference</span></span>](events-general-reference.md)
