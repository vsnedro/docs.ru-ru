---
title: События сборки мусора (трассировка событий Windows)
description: Просмотр подробных сведений о событиях трассировки событий Windows, собранных сборщиком мусора. В число рассмотренных событий входят GCStart_V1, GCEnd_V1, GCHeapStats_V1, GCCreateSegment_V1 и многое другое.
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 58ad874ef6a12c18c404640aa66577c391573534
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309746"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="e4ac5-104">События сборки мусора (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="e4ac5-105">Эти события собирают сведения, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="e4ac5-106">Они помогают при диагностике и отладке, в том числе позволяют определить, сколько раз осуществлялась сборка мусора, какой объем памяти был освобожден в ходе сборки мусора и т. д.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="e4ac5-107">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="e4ac5-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="e4ac5-108">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="e4ac5-109">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="e4ac5-110">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="e4ac5-111">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-111">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="e4ac5-112">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-112">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="e4ac5-113">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-113">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="e4ac5-114">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-114">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="e4ac5-115">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-115">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="e4ac5-116">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-116">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="e4ac5-117">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="e4ac5-117">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="e4ac5-118">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-118">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="e4ac5-119">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-119">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="e4ac5-120">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-120">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="e4ac5-121">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-121">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="e4ac5-122">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-122">GCStart_V1 Event</span></span>  

<span data-ttu-id="e4ac5-123">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-123">The following table shows the keyword and level.</span></span> <span data-ttu-id="e4ac5-124">Дополнительные сведения см. в разделе [Ключевые слова и уровни ETW среды CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-124">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="e4ac5-125">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-125">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-126">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-127">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-127">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-128">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-128">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-129">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-129">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-130">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-130">Event</span></span>|<span data-ttu-id="e4ac5-131">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-131">Event ID</span></span>|<span data-ttu-id="e4ac5-132">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="e4ac5-133">1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-133">1</span></span>|<span data-ttu-id="e4ac5-134">Сборка мусора начата.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-134">A garbage collection has started.</span></span>|

<span data-ttu-id="e4ac5-135">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-135">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-136">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-136">Field name</span></span>|<span data-ttu-id="e4ac5-137">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-137">Data type</span></span>|<span data-ttu-id="e4ac5-138">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-138">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-139">Количество</span><span class="sxs-lookup"><span data-stu-id="e4ac5-139">Count</span></span>|<span data-ttu-id="e4ac5-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-140">win:UInt32</span></span>|<span data-ttu-id="e4ac5-141">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-141">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="e4ac5-142">Глубина</span><span class="sxs-lookup"><span data-stu-id="e4ac5-142">Depth</span></span>|<span data-ttu-id="e4ac5-143">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-143">win:UInt32</span></span>|<span data-ttu-id="e4ac5-144">Поколение, для которого выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-144">The generation that is being collected.</span></span>|
|<span data-ttu-id="e4ac5-145">Причина</span><span class="sxs-lookup"><span data-stu-id="e4ac5-145">Reason</span></span>|<span data-ttu-id="e4ac5-146">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-146">win:UInt32</span></span>|<span data-ttu-id="e4ac5-147">Причина запуска сборки мусора:</span><span class="sxs-lookup"><span data-stu-id="e4ac5-147">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="e4ac5-148">0x0 — выделение кучи маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-148">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="e4ac5-149">0x1 — принудительная.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-149">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="e4ac5-150">0x2 — недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-150">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="e4ac5-151">0x3 — пусто.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-151">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="e4ac5-152">0x4 — выделение кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-152">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="e4ac5-153">0x5 — недостаточно места (для кучи маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-153">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="e4ac5-154">0x6 — недостаточно места (для кучи больших объектов).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-154">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="e4ac5-155">0x7 — принудительная, но не блокирующий.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-155">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="e4ac5-156">Тип</span><span class="sxs-lookup"><span data-stu-id="e4ac5-156">Type</span></span>|<span data-ttu-id="e4ac5-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-157">win:UInt32</span></span>|<span data-ttu-id="e4ac5-158">0x0 — блокировка сборки мусора вне фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-158">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="e4ac5-159">0x1 — фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-159">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="e4ac5-160">0x2 — блокировка сборки мусора в ходе фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-160">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="e4ac5-161">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-161">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-162">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-162">win:UInt16</span></span>|<span data-ttu-id="e4ac5-163">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="e4ac5-164">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-164">GCEnd_V1 Event</span></span>

<span data-ttu-id="e4ac5-165">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-165">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-166">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-166">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-167">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-168">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-168">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-169">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-169">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-170">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-170">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-171">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-171">Event</span></span>|<span data-ttu-id="e4ac5-172">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-172">Event ID</span></span>|<span data-ttu-id="e4ac5-173">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="e4ac5-174">2</span><span class="sxs-lookup"><span data-stu-id="e4ac5-174">2</span></span>|<span data-ttu-id="e4ac5-175">Сборка мусора закончена.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-175">The garbage collection has ended.</span></span>|

<span data-ttu-id="e4ac5-176">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-176">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-177">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-177">Field name</span></span>|<span data-ttu-id="e4ac5-178">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-178">Data type</span></span>|<span data-ttu-id="e4ac5-179">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-179">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-180">Количество</span><span class="sxs-lookup"><span data-stu-id="e4ac5-180">Count</span></span>|<span data-ttu-id="e4ac5-181">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-181">win:UInt32</span></span>|<span data-ttu-id="e4ac5-182">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-182">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="e4ac5-183">Глубина</span><span class="sxs-lookup"><span data-stu-id="e4ac5-183">Depth</span></span>|<span data-ttu-id="e4ac5-184">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-184">win:UInt32</span></span>|<span data-ttu-id="e4ac5-185">Поколение, для которого выполнялась сборка.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-185">The generation that was collected.</span></span>|
|<span data-ttu-id="e4ac5-186">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-186">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-187">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-187">win:UInt16</span></span>|<span data-ttu-id="e4ac5-188">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-188">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="e4ac5-189">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-189">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="e4ac5-190">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-190">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-191">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-191">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-192">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-192">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-194">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-194">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-195">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-195">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-196">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-196">Event</span></span>|<span data-ttu-id="e4ac5-197">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-197">Event ID</span></span>|<span data-ttu-id="e4ac5-198">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-198">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="e4ac5-199">4</span><span class="sxs-lookup"><span data-stu-id="e4ac5-199">4</span></span>|<span data-ttu-id="e4ac5-200">Показывает статистику кучи по завершении каждой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-200">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="e4ac5-201">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-201">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-202">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-202">Field name</span></span>|<span data-ttu-id="e4ac5-203">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-203">Data type</span></span>|<span data-ttu-id="e4ac5-204">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-204">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="e4ac5-205">GenerationSize0</span></span>|<span data-ttu-id="e4ac5-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-206">win:UInt64</span></span>|<span data-ttu-id="e4ac5-207">Размер области памяти поколения 0 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-207">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="e4ac5-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="e4ac5-208">TotalPromotedSize0</span></span>|<span data-ttu-id="e4ac5-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-209">win:UInt64</span></span>|<span data-ttu-id="e4ac5-210">Число байт, которые были переданы из поколения 0 в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="e4ac5-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-211">GenerationSize1</span></span>|<span data-ttu-id="e4ac5-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-212">win:UInt64</span></span>|<span data-ttu-id="e4ac5-213">Размер области памяти поколения 1 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-213">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="e4ac5-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-214">TotalPromotedSize1</span></span>|<span data-ttu-id="e4ac5-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-215">win:UInt64</span></span>|<span data-ttu-id="e4ac5-216">Число байт, которые были переданы из поколения 1 в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="e4ac5-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="e4ac5-217">GenerationSize2</span></span>|<span data-ttu-id="e4ac5-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-218">win:UInt64</span></span>|<span data-ttu-id="e4ac5-219">Размер области памяти поколения 2 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-219">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="e4ac5-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="e4ac5-220">TotalPromotedSize2</span></span>|<span data-ttu-id="e4ac5-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-221">win:UInt64</span></span>|<span data-ttu-id="e4ac5-222">Число байт, оставшихся в поколении 2 после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="e4ac5-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="e4ac5-223">GenerationSize3</span></span>|<span data-ttu-id="e4ac5-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-224">win:UInt64</span></span>|<span data-ttu-id="e4ac5-225">Размер кучи больших объектов (в байтах).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-225">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="e4ac5-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="e4ac5-226">TotalPromotedSize3</span></span>|<span data-ttu-id="e4ac5-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-227">win:UInt64</span></span>|<span data-ttu-id="e4ac5-228">Число байт, оставшихся в куче больших объектов после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="e4ac5-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="e4ac5-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="e4ac5-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-230">win:UInt64</span></span>|<span data-ttu-id="e4ac5-231">Общий размер (в байтах) объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="e4ac5-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="e4ac5-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="e4ac5-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-233">win:UInt64</span></span>|<span data-ttu-id="e4ac5-234">Количество объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-234">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="e4ac5-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="e4ac5-235">PinnedObjectCount</span></span>|<span data-ttu-id="e4ac5-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-236">win:UInt32</span></span>|<span data-ttu-id="e4ac5-237">Количество закрепленных (неподвижных) объектов.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-237">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="e4ac5-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="e4ac5-238">SinkBlockCount</span></span>|<span data-ttu-id="e4ac5-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-239">win:UInt32</span></span>|<span data-ttu-id="e4ac5-240">Количество используемых блоков синхронизации.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-240">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="e4ac5-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="e4ac5-241">GCHandleCount</span></span>|<span data-ttu-id="e4ac5-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-242">win:UInt32</span></span>|<span data-ttu-id="e4ac5-243">Число используемых дескрипторов сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-243">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="e4ac5-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-244">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-245">win:UInt16</span></span>|<span data-ttu-id="e4ac5-246">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="e4ac5-247">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-247">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="e4ac5-248">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-248">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-249">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-249">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-250">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-250">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-251">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-251">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-252">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-252">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-253">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-253">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-254">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-254">Event</span></span>|<span data-ttu-id="e4ac5-255">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-255">Event ID</span></span>|<span data-ttu-id="e4ac5-256">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-256">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="e4ac5-257">5</span><span class="sxs-lookup"><span data-stu-id="e4ac5-257">5</span></span>|<span data-ttu-id="e4ac5-258">Был создан новый сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-258">A new garbage collection segment has been created.</span></span> <span data-ttu-id="e4ac5-259">Кроме того, при включении трассировки для уже работающего процесса это событие создается для каждого существующего сегмента.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-259">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="e4ac5-260">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-260">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-261">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-261">Field name</span></span>|<span data-ttu-id="e4ac5-262">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-262">Data type</span></span>|<span data-ttu-id="e4ac5-263">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-263">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-264">Адрес</span><span class="sxs-lookup"><span data-stu-id="e4ac5-264">Address</span></span>|<span data-ttu-id="e4ac5-265">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-265">win:UInt64</span></span>|<span data-ttu-id="e4ac5-266">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-266">The address of the segment.</span></span>|
|<span data-ttu-id="e4ac5-267">Размер</span><span class="sxs-lookup"><span data-stu-id="e4ac5-267">Size</span></span>|<span data-ttu-id="e4ac5-268">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-268">win:UInt64</span></span>|<span data-ttu-id="e4ac5-269">Размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-269">The size of the segment.</span></span>|
|<span data-ttu-id="e4ac5-270">Тип</span><span class="sxs-lookup"><span data-stu-id="e4ac5-270">Type</span></span>|<span data-ttu-id="e4ac5-271">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-271">win:UInt32</span></span>|<span data-ttu-id="e4ac5-272">0x0 — куча маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-272">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="e4ac5-273">0x1 — куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-273">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="e4ac5-274">0x2 — куча только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-274">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="e4ac5-275">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-275">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-276">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-276">win:UInt16</span></span>|<span data-ttu-id="e4ac5-277">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-277">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="e4ac5-278">Обратите внимание, что размер сегментов, выделенных сборщиком мусора, зависит от реализации и может быть изменен в любое время, в том числе при периодических обновлениях.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-278">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="e4ac5-279">Приложение не должно делать никаких допущений относительно размера определенного сегмента, полагаться на него или пытаться настроить объем памяти, доступный для выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-279">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="e4ac5-280">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-280">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="e4ac5-281">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-281">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-282">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-282">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-283">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-283">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-284">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-284">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-285">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-285">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-286">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-286">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-287">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-287">Event</span></span>|<span data-ttu-id="e4ac5-288">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-288">Event ID</span></span>|<span data-ttu-id="e4ac5-289">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-289">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="e4ac5-290">6</span><span class="sxs-lookup"><span data-stu-id="e4ac5-290">6</span></span>|<span data-ttu-id="e4ac5-291">Сегмент сборки мусора был освобожден.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-291">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="e4ac5-292">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-292">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-293">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-293">Field name</span></span>|<span data-ttu-id="e4ac5-294">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-294">Data type</span></span>|<span data-ttu-id="e4ac5-295">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-295">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-296">Адрес</span><span class="sxs-lookup"><span data-stu-id="e4ac5-296">Address</span></span>|<span data-ttu-id="e4ac5-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-297">win:UInt64</span></span>|<span data-ttu-id="e4ac5-298">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-298">The address of the segment.</span></span>|
|<span data-ttu-id="e4ac5-299">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-299">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-300">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-300">win:UInt16</span></span>|<span data-ttu-id="e4ac5-301">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-301">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="e4ac5-302">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-302">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="e4ac5-303">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-303">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-304">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-304">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-305">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-305">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-306">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-306">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-307">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-307">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-308">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-308">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-309">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-309">Event</span></span>|<span data-ttu-id="e4ac5-310">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-310">Event ID</span></span>|<span data-ttu-id="e4ac5-311">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-311">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="e4ac5-312">7</span><span class="sxs-lookup"><span data-stu-id="e4ac5-312">7</span></span>|<span data-ttu-id="e4ac5-313">Началось возобновление приостановленной среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-313">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="e4ac5-314">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-314">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="e4ac5-315">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-315">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="e4ac5-316">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-316">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-317">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-317">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-318">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-318">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-319">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-319">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-320">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-320">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-321">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-321">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-322">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-322">Event</span></span>|<span data-ttu-id="e4ac5-323">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-323">Event Id</span></span>|<span data-ttu-id="e4ac5-324">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-324">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="e4ac5-325">3</span><span class="sxs-lookup"><span data-stu-id="e4ac5-325">3</span></span>|<span data-ttu-id="e4ac5-326">Возобновление приостановленной среды CLR завершено.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-326">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="e4ac5-327">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-327">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="e4ac5-328">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-328">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="e4ac5-329">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-329">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-330">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-330">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-331">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-331">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-332">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-332">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-333">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-333">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-334">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-334">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-335">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-335">Event</span></span>|<span data-ttu-id="e4ac5-336">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-336">Event ID</span></span>|<span data-ttu-id="e4ac5-337">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-337">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="e4ac5-338">9</span><span class="sxs-lookup"><span data-stu-id="e4ac5-338">9</span></span>|<span data-ttu-id="e4ac5-339">Началась приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-339">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="e4ac5-340">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-340">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-341">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-341">Field name</span></span>|<span data-ttu-id="e4ac5-342">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-342">Data type</span></span>|<span data-ttu-id="e4ac5-343">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-343">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-344">Причина</span><span class="sxs-lookup"><span data-stu-id="e4ac5-344">Reason</span></span>|<span data-ttu-id="e4ac5-345">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-345">win:UInt16</span></span>|<span data-ttu-id="e4ac5-346">0x0 — другое.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-346">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="e4ac5-347">0x1 — сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-347">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="e4ac5-348">0x2 — завершение работы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-348">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="e4ac5-349">0x3 — свертка кода.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-349">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="e4ac5-350">0x4 — завершение работы.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-350">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="e4ac5-351">0x5 — отладчик.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-351">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="e4ac5-352">0x6 — подготовка к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-352">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="e4ac5-353">Количество</span><span class="sxs-lookup"><span data-stu-id="e4ac5-353">Count</span></span>|<span data-ttu-id="e4ac5-354">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-354">win:UInt32</span></span>|<span data-ttu-id="e4ac5-355">Счетчик сборки мусора на текущий момент времени.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-355">The GC count at the time.</span></span> <span data-ttu-id="e4ac5-356">Обычно после этого отображается последующее событие запуска сборки мусора, а значение увеличивается на 1 в соответствии с увеличением индекса сборки мусора в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-356">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="e4ac5-357">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-357">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-358">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-358">win:UInt16</span></span>|<span data-ttu-id="e4ac5-359">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-359">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="e4ac5-360">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-360">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="e4ac5-361">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-361">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-362">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-362">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-363">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-363">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-364">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-364">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-365">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-365">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-366">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-366">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-367">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-367">Event</span></span>|<span data-ttu-id="e4ac5-368">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-368">Event ID</span></span>|<span data-ttu-id="e4ac5-369">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-369">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="e4ac5-370">8</span><span class="sxs-lookup"><span data-stu-id="e4ac5-370">8</span></span>|<span data-ttu-id="e4ac5-371">Завершена приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-371">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="e4ac5-372">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-372">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="e4ac5-373">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="e4ac5-373">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="e4ac5-374">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-374">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-375">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-375">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-376">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-376">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-377">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-377">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-378">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-378">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-379">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-379">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-380">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-380">Event</span></span>|<span data-ttu-id="e4ac5-381">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-381">Event ID</span></span>|<span data-ttu-id="e4ac5-382">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-382">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="e4ac5-383">10</span><span class="sxs-lookup"><span data-stu-id="e4ac5-383">10</span></span>|<span data-ttu-id="e4ac5-384">Каждый раз выделяется около 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-384">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="e4ac5-385">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-385">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-386">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-386">Field name</span></span>|<span data-ttu-id="e4ac5-387">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-387">Data type</span></span>|<span data-ttu-id="e4ac5-388">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-388">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-389">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="e4ac5-389">AllocationAmount</span></span>|<span data-ttu-id="e4ac5-390">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-390">win:UInt32</span></span>|<span data-ttu-id="e4ac5-391">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-391">The allocation size, in bytes.</span></span> <span data-ttu-id="e4ac5-392">Это значение является точным для выделений, размер которых меньше длины ULONG (4 294 967 295 байт).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-392">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="e4ac5-393">Если выделение больше, это поле содержит усеченное значение.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-393">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="e4ac5-394">Используйте `AllocationAmount64` для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-394">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="e4ac5-395">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="e4ac5-395">AllocationKind</span></span>|<span data-ttu-id="e4ac5-396">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-396">win:UInt32</span></span>|<span data-ttu-id="e4ac5-397">0x0 — выделение для маленького объекта (выделение в куче маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-397">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="e4ac5-398">0x1 — выделение для большого объекта (выделение в куче больших объектов).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-398">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="e4ac5-399">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-399">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-400">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-400">win:UInt16</span></span>|<span data-ttu-id="e4ac5-401">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-401">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="e4ac5-402">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-402">AllocationAmount64</span></span>|<span data-ttu-id="e4ac5-403">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e4ac5-403">win:UInt64</span></span>|<span data-ttu-id="e4ac5-404">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-404">The allocation size, in bytes.</span></span> <span data-ttu-id="e4ac5-405">Это значение является точным для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-405">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="e4ac5-406">TypeId</span><span class="sxs-lookup"><span data-stu-id="e4ac5-406">TypeId</span></span>|<span data-ttu-id="e4ac5-407">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="e4ac5-407">win:Pointer</span></span>|<span data-ttu-id="e4ac5-408">Адрес MethodTable.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-408">The address of the MethodTable.</span></span> <span data-ttu-id="e4ac5-409">Если в ходе этого события было выделено несколько типов объектов, указывается адрес MethodTable, соответствующий последнему выделенному объекту (объекту, вызвавшему превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-409">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="e4ac5-410">TypeName</span><span class="sxs-lookup"><span data-stu-id="e4ac5-410">TypeName</span></span>|<span data-ttu-id="e4ac5-411">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4ac5-411">win:UnicodeString</span></span>|<span data-ttu-id="e4ac5-412">Имя выделенного типа.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-412">The name of the type that was allocated.</span></span> <span data-ttu-id="e4ac5-413">Если в ходе этого события было выделено несколько типов объектов, указывается тип последнего выделенного объекта (объекта, вызвавшего превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="e4ac5-413">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="e4ac5-414">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="e4ac5-414">HeapIndex</span></span>|<span data-ttu-id="e4ac5-415">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-415">win:UInt32</span></span>|<span data-ttu-id="e4ac5-416">Куча, в которой был выделен объект.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-416">The heap where the object was allocated.</span></span> <span data-ttu-id="e4ac5-417">Это значение равно 0 (нулю) при выполнении сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-417">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="e4ac5-418">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-418">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="e4ac5-419">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-419">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-420">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-420">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-421">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-421">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-422">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-422">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-423">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-423">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-424">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-424">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-425">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-425">Event</span></span>|<span data-ttu-id="e4ac5-426">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-426">Event ID</span></span>|<span data-ttu-id="e4ac5-427">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-427">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="e4ac5-428">14</span><span class="sxs-lookup"><span data-stu-id="e4ac5-428">14</span></span>|<span data-ttu-id="e4ac5-429">Начало выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-429">The start of running finalizers.</span></span>|

<span data-ttu-id="e4ac5-430">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-430">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="e4ac5-431">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-431">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="e4ac5-432">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-432">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-433">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-433">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-434">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-435">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-435">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-436">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-436">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-437">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-437">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-438">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-438">Event</span></span>|<span data-ttu-id="e4ac5-439">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-439">Event ID</span></span>|<span data-ttu-id="e4ac5-440">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-440">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="e4ac5-441">13</span><span class="sxs-lookup"><span data-stu-id="e4ac5-441">13</span></span>|<span data-ttu-id="e4ac5-442">Завершение выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-442">The end of running finalizers.</span></span>|

<span data-ttu-id="e4ac5-443">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-443">The following table shows the event data:</span></span>

|<span data-ttu-id="e4ac5-444">Имя поля</span><span class="sxs-lookup"><span data-stu-id="e4ac5-444">Field name</span></span>|<span data-ttu-id="e4ac5-445">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e4ac5-445">Data type</span></span>|<span data-ttu-id="e4ac5-446">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ac5-446">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e4ac5-447">Количество</span><span class="sxs-lookup"><span data-stu-id="e4ac5-447">Count</span></span>|<span data-ttu-id="e4ac5-448">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4ac5-448">win:UInt32</span></span>|<span data-ttu-id="e4ac5-449">Число выполненных методов завершения.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-449">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="e4ac5-450">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4ac5-450">ClrInstanceID</span></span>|<span data-ttu-id="e4ac5-451">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4ac5-451">win:UInt16</span></span>|<span data-ttu-id="e4ac5-452">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-452">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="e4ac5-453">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-453">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="e4ac5-454">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-454">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-455">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-455">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-456">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-456">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-457">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-457">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-458">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-458">Informational (4)</span></span>|
|<span data-ttu-id="e4ac5-459">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-459">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e4ac5-460">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-460">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-461">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-461">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-462">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-462">Event</span></span>|<span data-ttu-id="e4ac5-463">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-463">Event ID</span></span>|<span data-ttu-id="e4ac5-464">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-464">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="e4ac5-465">11</span><span class="sxs-lookup"><span data-stu-id="e4ac5-465">11</span></span>|<span data-ttu-id="e4ac5-466">Был создан параллельный поток сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-466">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="e4ac5-467">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-467">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="e4ac5-468">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="e4ac5-468">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="e4ac5-469">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-469">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e4ac5-470">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-470">Keyword for raising the event</span></span>|<span data-ttu-id="e4ac5-471">Level</span><span class="sxs-lookup"><span data-stu-id="e4ac5-471">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e4ac5-472">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-472">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e4ac5-473">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-473">Informational (4)</span></span>|
|<span data-ttu-id="e4ac5-474">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-474">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e4ac5-475">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="e4ac5-475">Informational (4)</span></span>|

<span data-ttu-id="e4ac5-476">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-476">The following table shows the event information:</span></span>

|<span data-ttu-id="e4ac5-477">Событие</span><span class="sxs-lookup"><span data-stu-id="e4ac5-477">Event</span></span>|<span data-ttu-id="e4ac5-478">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e4ac5-478">Event ID</span></span>|<span data-ttu-id="e4ac5-479">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="e4ac5-479">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="e4ac5-480">12</span><span class="sxs-lookup"><span data-stu-id="e4ac5-480">12</span></span>|<span data-ttu-id="e4ac5-481">Параллельный поток сборки мусора был завершен.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-481">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="e4ac5-482">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="e4ac5-482">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ac5-483">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e4ac5-483">See also</span></span>

- [<span data-ttu-id="e4ac5-484">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="e4ac5-484">CLR ETW Events</span></span>](clr-etw-events.md)
