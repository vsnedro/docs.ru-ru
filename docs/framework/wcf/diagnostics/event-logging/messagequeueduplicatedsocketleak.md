---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: e7ccbdce37981dfd8971f0d7ef0031b52cad2379
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262441"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="07d2d-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="07d2d-102">MessageQueueDuplicatedSocketLeak</span></span>

<span data-ttu-id="07d2d-103">Идентификатор: 165</span><span class="sxs-lookup"><span data-stu-id="07d2d-103">Id: 165</span></span>  
  
 <span data-ttu-id="07d2d-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="07d2d-104">Severity: Error</span></span>  
  
 <span data-ttu-id="07d2d-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="07d2d-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="07d2d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="07d2d-106">Description</span></span>  

 <span data-ttu-id="07d2d-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="07d2d-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="07d2d-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="07d2d-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="07d2d-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="07d2d-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d2d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="07d2d-110">See also</span></span>

- [<span data-ttu-id="07d2d-111">Ведение журналов событий</span><span class="sxs-lookup"><span data-stu-id="07d2d-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="07d2d-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="07d2d-112">Events General Reference</span></span>](events-general-reference.md)
