---
title: События отслеживания ресурсов домена приложения (трассировка событий Windows)
description: Узнайте о событиях отслеживания ресурсов в домене приложений (ARM) в .NET, таких как ThreadCreated, событие appdomainmemallocated, событие appdomainmemsurvived и др.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309785"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="30f13-103">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="30f13-103">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="30f13-104">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="30f13-104">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="30f13-105">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="30f13-105">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="30f13-106">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="30f13-106">ThreadCreated Event</span></span>

<span data-ttu-id="30f13-107">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="30f13-107">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="30f13-108">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="30f13-108">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="30f13-109">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="30f13-109">The following table shows the keyword and level.</span></span> <span data-ttu-id="30f13-110">Дополнительные сведения см. в разделе [Ключевые слова и уровни ETW среды CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="30f13-110">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="30f13-111">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="30f13-111">Keyword for raising the event</span></span>|<span data-ttu-id="30f13-112">Level</span><span class="sxs-lookup"><span data-stu-id="30f13-112">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30f13-113">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30f13-113">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30f13-114">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-114">Informational(4)</span></span>|
|<span data-ttu-id="30f13-115">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30f13-115">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30f13-116">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-116">Informational(4)</span></span>|

<span data-ttu-id="30f13-117">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="30f13-117">The following table shows the event information:</span></span>

|<span data-ttu-id="30f13-118">Событие</span><span class="sxs-lookup"><span data-stu-id="30f13-118">Event</span></span>|<span data-ttu-id="30f13-119">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="30f13-119">Event ID</span></span>|<span data-ttu-id="30f13-120">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="30f13-120">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="30f13-121">85</span><span class="sxs-lookup"><span data-stu-id="30f13-121">85</span></span>|<span data-ttu-id="30f13-122">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="30f13-122">A thread was created for the application domain.</span></span>|

<span data-ttu-id="30f13-123">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="30f13-123">The following table shows the event data:</span></span>

|<span data-ttu-id="30f13-124">Имя поля</span><span class="sxs-lookup"><span data-stu-id="30f13-124">Field name</span></span>|<span data-ttu-id="30f13-125">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30f13-125">Data type</span></span>|<span data-ttu-id="30f13-126">Описание</span><span class="sxs-lookup"><span data-stu-id="30f13-126">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30f13-127">ThreadID</span><span class="sxs-lookup"><span data-stu-id="30f13-127">ThreadID</span></span>|<span data-ttu-id="30f13-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-128">win:UInt64</span></span>|<span data-ttu-id="30f13-129">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="30f13-129">ID of the thread that was created.</span></span>|
|<span data-ttu-id="30f13-130">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30f13-130">AppDomainID</span></span>|<span data-ttu-id="30f13-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-131">win:UInt64</span></span>|<span data-ttu-id="30f13-132">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="30f13-132">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="30f13-133">Флаги</span><span class="sxs-lookup"><span data-stu-id="30f13-133">Flags</span></span>|<span data-ttu-id="30f13-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30f13-134">win:UInt32</span></span>|<span data-ttu-id="30f13-135">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="30f13-135">Thread creation flags.</span></span>|
|<span data-ttu-id="30f13-136">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="30f13-136">ManagedThreadIndex</span></span>|<span data-ttu-id="30f13-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30f13-137">win:UInt32</span></span>|<span data-ttu-id="30f13-138">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="30f13-138">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="30f13-139">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="30f13-139">OSThreadID</span></span>|<span data-ttu-id="30f13-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30f13-140">win:UInt32</span></span>|<span data-ttu-id="30f13-141">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="30f13-141">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="30f13-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30f13-142">ClrInstanceID</span></span>|<span data-ttu-id="30f13-143">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30f13-143">win:UInt16</span></span>|<span data-ttu-id="30f13-144">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30f13-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="30f13-145">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="30f13-145">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="30f13-146">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="30f13-146">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30f13-147">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="30f13-147">Keyword for raising the event</span></span>|<span data-ttu-id="30f13-148">Level</span><span class="sxs-lookup"><span data-stu-id="30f13-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30f13-149">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30f13-149">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30f13-150">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-150">Informational(4)</span></span>|

<span data-ttu-id="30f13-151">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="30f13-151">The following table shows the event information:</span></span>

|<span data-ttu-id="30f13-152">Событие</span><span class="sxs-lookup"><span data-stu-id="30f13-152">Event</span></span>|<span data-ttu-id="30f13-153">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="30f13-153">Event ID</span></span>|<span data-ttu-id="30f13-154">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="30f13-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="30f13-155">83</span><span class="sxs-lookup"><span data-stu-id="30f13-155">83</span></span>|<span data-ttu-id="30f13-156">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="30f13-156">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="30f13-157">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="30f13-157">The following table shows the event data:</span></span>

|<span data-ttu-id="30f13-158">Имя поля</span><span class="sxs-lookup"><span data-stu-id="30f13-158">Field name</span></span>|<span data-ttu-id="30f13-159">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30f13-159">Data type</span></span>|<span data-ttu-id="30f13-160">Описание</span><span class="sxs-lookup"><span data-stu-id="30f13-160">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30f13-161">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30f13-161">AppDomainID</span></span>|<span data-ttu-id="30f13-162">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-162">win:UInt64</span></span>|<span data-ttu-id="30f13-163">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="30f13-163">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="30f13-164">Allocated</span><span class="sxs-lookup"><span data-stu-id="30f13-164">Allocated</span></span>|<span data-ttu-id="30f13-165">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-165">win:UInt64</span></span>|<span data-ttu-id="30f13-166">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="30f13-166">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="30f13-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30f13-167">ClrInstanceID</span></span>|<span data-ttu-id="30f13-168">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30f13-168">win:UInt16</span></span>|<span data-ttu-id="30f13-169">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30f13-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="30f13-170">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="30f13-170">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="30f13-171">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="30f13-171">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30f13-172">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="30f13-172">Keyword for raising the event</span></span>|<span data-ttu-id="30f13-173">Level</span><span class="sxs-lookup"><span data-stu-id="30f13-173">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30f13-174">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30f13-174">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30f13-175">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-175">Informational(4)</span></span>|

<span data-ttu-id="30f13-176">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="30f13-176">The following table shows the event information:</span></span>

|<span data-ttu-id="30f13-177">Событие</span><span class="sxs-lookup"><span data-stu-id="30f13-177">Event</span></span>|<span data-ttu-id="30f13-178">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="30f13-178">Event ID</span></span>|<span data-ttu-id="30f13-179">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="30f13-179">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="30f13-180">84</span><span class="sxs-lookup"><span data-stu-id="30f13-180">84</span></span>|<span data-ttu-id="30f13-181">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="30f13-181">Each garbage collection has ended.</span></span>|

<span data-ttu-id="30f13-182">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="30f13-182">The following table shows the event data:</span></span>

|<span data-ttu-id="30f13-183">Имя поля</span><span class="sxs-lookup"><span data-stu-id="30f13-183">Field name</span></span>|<span data-ttu-id="30f13-184">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30f13-184">Data type</span></span>|<span data-ttu-id="30f13-185">Описание</span><span class="sxs-lookup"><span data-stu-id="30f13-185">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30f13-186">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30f13-186">AppDomainID</span></span>|<span data-ttu-id="30f13-187">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-187">win:UInt64</span></span>|<span data-ttu-id="30f13-188">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="30f13-188">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="30f13-189">Survived</span><span class="sxs-lookup"><span data-stu-id="30f13-189">Survived</span></span>|<span data-ttu-id="30f13-190">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-190">win:UInt64</span></span>|<span data-ttu-id="30f13-191">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="30f13-191">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="30f13-192">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="30f13-192">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="30f13-193">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="30f13-193">ProcessSurvived</span></span>|<span data-ttu-id="30f13-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-194">win:UInt64</span></span>|<span data-ttu-id="30f13-195">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="30f13-195">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="30f13-196">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="30f13-196">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="30f13-197">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="30f13-197">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="30f13-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30f13-198">ClrInstanceID</span></span>|<span data-ttu-id="30f13-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30f13-199">win:UInt16</span></span>|<span data-ttu-id="30f13-200">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30f13-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="30f13-201">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="30f13-201">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="30f13-202">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="30f13-202">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30f13-203">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="30f13-203">Keyword for raising the event</span></span>|<span data-ttu-id="30f13-204">Level</span><span class="sxs-lookup"><span data-stu-id="30f13-204">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30f13-205">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30f13-205">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30f13-206">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-206">Informational(4)</span></span>|
|<span data-ttu-id="30f13-207">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30f13-207">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30f13-208">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-208">Informational(4)</span></span>|

<span data-ttu-id="30f13-209">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="30f13-209">The following table shows the event information:</span></span>

|<span data-ttu-id="30f13-210">Событие</span><span class="sxs-lookup"><span data-stu-id="30f13-210">Event</span></span>|<span data-ttu-id="30f13-211">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="30f13-211">Event ID</span></span>|<span data-ttu-id="30f13-212">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="30f13-212">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="30f13-213">87</span><span class="sxs-lookup"><span data-stu-id="30f13-213">87</span></span>|<span data-ttu-id="30f13-214">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="30f13-214">A thread enters an application domain.</span></span>|

<span data-ttu-id="30f13-215">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="30f13-215">The following table shows the event data:</span></span>

|<span data-ttu-id="30f13-216">Имя поля</span><span class="sxs-lookup"><span data-stu-id="30f13-216">Field name</span></span>|<span data-ttu-id="30f13-217">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30f13-217">Data type</span></span>|<span data-ttu-id="30f13-218">Описание</span><span class="sxs-lookup"><span data-stu-id="30f13-218">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30f13-219">ThreadID</span><span class="sxs-lookup"><span data-stu-id="30f13-219">ThreadID</span></span>|<span data-ttu-id="30f13-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-220">win:UInt64</span></span>|<span data-ttu-id="30f13-221">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="30f13-221">The thread identifier.</span></span>|
|<span data-ttu-id="30f13-222">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30f13-222">AppDomainID</span></span>|<span data-ttu-id="30f13-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-223">win:UInt64</span></span>|<span data-ttu-id="30f13-224">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="30f13-224">The application domain identifier.</span></span>|
|<span data-ttu-id="30f13-225">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30f13-225">ClrInstanceID</span></span>|<span data-ttu-id="30f13-226">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30f13-226">win:UInt16</span></span>|<span data-ttu-id="30f13-227">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30f13-227">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="30f13-228">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="30f13-228">ThreadTerminated Event</span></span>

<span data-ttu-id="30f13-229">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="30f13-229">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="30f13-230">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="30f13-230">Keyword for raising the event</span></span>|<span data-ttu-id="30f13-231">Level</span><span class="sxs-lookup"><span data-stu-id="30f13-231">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="30f13-232">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="30f13-232">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="30f13-233">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-233">Informational(4)</span></span>|
|<span data-ttu-id="30f13-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30f13-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30f13-235">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="30f13-235">Informational(4)</span></span>|

<span data-ttu-id="30f13-236">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="30f13-236">The following table shows the event information:</span></span>

|<span data-ttu-id="30f13-237">Событие</span><span class="sxs-lookup"><span data-stu-id="30f13-237">Event</span></span>|<span data-ttu-id="30f13-238">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="30f13-238">Event ID</span></span>|<span data-ttu-id="30f13-239">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="30f13-239">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="30f13-240">86</span><span class="sxs-lookup"><span data-stu-id="30f13-240">86</span></span>|<span data-ttu-id="30f13-241">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="30f13-241">A thread terminates.</span></span>|

<span data-ttu-id="30f13-242">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="30f13-242">The following table shows the event data:</span></span>

|<span data-ttu-id="30f13-243">Имя поля</span><span class="sxs-lookup"><span data-stu-id="30f13-243">Field name</span></span>|<span data-ttu-id="30f13-244">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30f13-244">Data type</span></span>|<span data-ttu-id="30f13-245">Описание</span><span class="sxs-lookup"><span data-stu-id="30f13-245">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="30f13-246">ThreadID</span><span class="sxs-lookup"><span data-stu-id="30f13-246">ThreadID</span></span>|<span data-ttu-id="30f13-247">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-247">win:UInt64</span></span>|<span data-ttu-id="30f13-248">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="30f13-248">The thread identifier.</span></span>|
|<span data-ttu-id="30f13-249">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="30f13-249">AppDomainID</span></span>|<span data-ttu-id="30f13-250">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30f13-250">win:UInt64</span></span>|<span data-ttu-id="30f13-251">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="30f13-251">The application domain identifier.</span></span>|
|<span data-ttu-id="30f13-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30f13-252">ClrInstanceID</span></span>|<span data-ttu-id="30f13-253">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30f13-253">win:UInt16</span></span>|<span data-ttu-id="30f13-254">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30f13-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="30f13-255">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="30f13-255">See also</span></span>

- [<span data-ttu-id="30f13-256">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="30f13-256">CLR ETW Events</span></span>](clr-etw-events.md)
