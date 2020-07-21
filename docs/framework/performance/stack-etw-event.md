---
title: События стека (трассировка событий Windows)
description: Прочтите сведения о событии трассировки событий Windows стека, которое следует использовать вместе с другими событиями для создания трассировок стека после возникновения события.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: cab496615c4ef17831895b72c8987917e3c06e77
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474141"
---
# <a name="stack-etw-event"></a><span data-ttu-id="09578-103">События стека (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="09578-103">Stack ETW Event</span></span>
<span data-ttu-id="09578-104">Событие стека должно использоваться вместе с другими событиями для создания трассировок стека после вызова события.</span><span class="sxs-lookup"><span data-stu-id="09578-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="09578-105">Оно регистрируется при включенном поставщике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="09578-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="09578-106">Это очень часто случающееся событие, так как оно сопровождает создание другого события времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="09578-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="09578-107">По этой причине рекомендуется использовать его с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="09578-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="09578-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="09578-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="09578-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="09578-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="09578-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="09578-110">Keyword for raising the event</span></span>|<span data-ttu-id="09578-111">Level</span><span class="sxs-lookup"><span data-stu-id="09578-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="09578-112">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="09578-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="09578-113">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="09578-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="09578-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="09578-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="09578-115">Событие</span><span class="sxs-lookup"><span data-stu-id="09578-115">Event</span></span>|<span data-ttu-id="09578-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="09578-116">Event ID</span></span>|<span data-ttu-id="09578-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="09578-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="09578-118">82</span><span class="sxs-lookup"><span data-stu-id="09578-118">82</span></span>|<span data-ttu-id="09578-119">Вместе с другими событиями для создания трассировок стека после этого события.</span><span class="sxs-lookup"><span data-stu-id="09578-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="09578-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="09578-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="09578-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="09578-121">Field name</span></span>|<span data-ttu-id="09578-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="09578-122">Data Type</span></span>|<span data-ttu-id="09578-123">Описание</span><span class="sxs-lookup"><span data-stu-id="09578-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="09578-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="09578-124">ClrInstanceID</span></span>|<span data-ttu-id="09578-125">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="09578-125">win:Uint16</span></span>|<span data-ttu-id="09578-126">Уникальный идентификатор среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="09578-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="09578-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="09578-127">Reserved1</span></span>|<span data-ttu-id="09578-128">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="09578-128">win:UInt8</span></span>|<span data-ttu-id="09578-129">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="09578-129">Reserved.</span></span>|  
|<span data-ttu-id="09578-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="09578-130">Reserved2</span></span>|<span data-ttu-id="09578-131">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="09578-131">win:UInt8</span></span>|<span data-ttu-id="09578-132">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="09578-132">Reserved.</span></span>|  
|<span data-ttu-id="09578-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="09578-133">FrameCount</span></span>|<span data-ttu-id="09578-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="09578-134">win:UInt32</span></span>|<span data-ttu-id="09578-135">Число кадров в трассировке стека.</span><span class="sxs-lookup"><span data-stu-id="09578-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="09578-136">Стек</span><span class="sxs-lookup"><span data-stu-id="09578-136">Stack</span></span>|<span data-ttu-id="09578-137">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="09578-137">win:Pointer</span></span>|<span data-ttu-id="09578-138">Столбцы указателей инструкций.</span><span class="sxs-lookup"><span data-stu-id="09578-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09578-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="09578-139">See also</span></span>

- [<span data-ttu-id="09578-140">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="09578-140">CLR ETW Events</span></span>](clr-etw-events.md)
