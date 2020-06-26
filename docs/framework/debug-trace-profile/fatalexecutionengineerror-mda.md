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
ms.openlocfilehash: 0806d2eaa1752c88bebd03304fbe5c8094416a48
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415931"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="3e2a4-103">Помощник по отладке управляемого кода fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="3e2a4-103">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="3e2a4-104">Помощник по отладке управляемого кода `fatalExecutionEngineError` (MDA) активируется при обнаружении неустранимой ошибки в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="3e2a4-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="3e2a4-105">В этом случае процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3e2a4-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="3e2a4-106">Symptoms</span></span>  
 <span data-ttu-id="3e2a4-107">Непредвиденное завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-107">Unexpected process termination.</span></span> <span data-ttu-id="3e2a4-108">Другие признаки определить невозможно, поскольку сбой среды CLR может происходить по самым разным причинам.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3e2a4-109">Причина</span><span class="sxs-lookup"><span data-stu-id="3e2a4-109">Cause</span></span>  
 <span data-ttu-id="3e2a4-110">Неустранимое повреждение среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="3e2a4-111">Чаще всего это вызвано повреждением данных, которое может быть связано с целым рядом проблем, таких как вызовы некорректных функций вызова неуправляемого кода и передача недопустимых данных в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3e2a4-112">Решение</span><span class="sxs-lookup"><span data-stu-id="3e2a4-112">Resolution</span></span>  
 <span data-ttu-id="3e2a4-113">Чтобы определить причины проблемы, попробуйте включить другие помощники по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="3e2a4-114">При диагностике вам могут помочь следующие помощники по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="3e2a4-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="3e2a4-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="3e2a4-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="3e2a4-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="3e2a4-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="3e2a4-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="3e2a4-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="3e2a4-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="3e2a4-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="3e2a4-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="3e2a4-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="3e2a4-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="3e2a4-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="3e2a4-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="3e2a4-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="3e2a4-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="3e2a4-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="3e2a4-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="3e2a4-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="3e2a4-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="3e2a4-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="3e2a4-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="3e2a4-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="3e2a4-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="3e2a4-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3e2a4-127">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="3e2a4-127">Effect on the Runtime</span></span>  
 <span data-ttu-id="3e2a4-128">Этот помощник по отладке управляемого кода не оказывает влияния на поведение среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3e2a4-129">Вывод</span><span class="sxs-lookup"><span data-stu-id="3e2a4-129">Output</span></span>  
 <span data-ttu-id="3e2a4-130">Адрес функции среды CLR, которая стала причиной неустранимой ошибки, идентификатор потока, в котором произошла ошибка, а также код самой ошибки.</span><span class="sxs-lookup"><span data-stu-id="3e2a4-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3e2a4-131">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="3e2a4-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e2a4-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3e2a4-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="3e2a4-133">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="3e2a4-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
