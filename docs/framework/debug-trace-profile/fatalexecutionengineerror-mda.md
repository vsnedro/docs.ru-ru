---
title: Помощник по отладке управляемого кода fatalExecutionEngineError
description: Ознакомьтесь с помощником по отладке управляемого кода (MDA) Фаталексекутионенгиниррор в .NET, который может активироваться из-за непредвиденного завершения процесса.
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
ms.openlocfilehash: a9347338d53755b74b3ff291f75cb6b221134130
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244279"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="cf52a-103">Помощник по отладке управляемого кода fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="cf52a-103">fatalExecutionEngineError MDA</span></span>

<span data-ttu-id="cf52a-104">Помощник по отладке управляемого кода `fatalExecutionEngineError` (MDA) активируется при обнаружении неустранимой ошибки в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="cf52a-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="cf52a-105">В этом случае процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="cf52a-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="cf52a-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="cf52a-106">Symptoms</span></span>  

 <span data-ttu-id="cf52a-107">Непредвиденное завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="cf52a-107">Unexpected process termination.</span></span> <span data-ttu-id="cf52a-108">Другие признаки определить невозможно, поскольку сбой среды CLR может происходить по самым разным причинам.</span><span class="sxs-lookup"><span data-stu-id="cf52a-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="cf52a-109">Причина:</span><span class="sxs-lookup"><span data-stu-id="cf52a-109">Cause</span></span>  

 <span data-ttu-id="cf52a-110">Неустранимое повреждение среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cf52a-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="cf52a-111">Чаще всего это вызвано повреждением данных, которое может быть связано с целым рядом проблем, таких как вызовы некорректных функций вызова неуправляемого кода и передача недопустимых данных в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="cf52a-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="cf52a-112">Разрешение</span><span class="sxs-lookup"><span data-stu-id="cf52a-112">Resolution</span></span>  

 <span data-ttu-id="cf52a-113">Чтобы определить причины проблемы, попробуйте включить другие помощники по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="cf52a-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="cf52a-114">При диагностике вам могут помочь следующие помощники по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="cf52a-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="cf52a-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="cf52a-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="cf52a-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="cf52a-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="cf52a-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="cf52a-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="cf52a-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="cf52a-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="cf52a-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="cf52a-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="cf52a-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="cf52a-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="cf52a-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="cf52a-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="cf52a-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="cf52a-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="cf52a-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="cf52a-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="cf52a-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="cf52a-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="cf52a-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="cf52a-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="cf52a-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="cf52a-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cf52a-127">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="cf52a-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="cf52a-128">Этот помощник по отладке управляемого кода не оказывает влияния на поведение среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="cf52a-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cf52a-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cf52a-129">Output</span></span>  

 <span data-ttu-id="cf52a-130">Адрес функции среды CLR, которая стала причиной неустранимой ошибки, идентификатор потока, в котором произошла ошибка, а также код самой ошибки.</span><span class="sxs-lookup"><span data-stu-id="cf52a-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="cf52a-131">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="cf52a-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf52a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cf52a-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="cf52a-133">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="cf52a-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
