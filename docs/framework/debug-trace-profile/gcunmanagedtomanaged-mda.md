---
title: gcUnmanagedToManaged MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Гкманажедтаунманажед в .NET. Этот MDA может активироваться из-за повреждения кучи мусора во время перехода на управляемый код.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
ms.openlocfilehash: 320d55224e6a204d330447d6c68eabe0fa6cf892
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415905"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="828af-104">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="828af-104">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="828af-105">Помощник по отладке управляемого кода (MDA) `gcUnmanagedToManaged` вызывает сбор мусора каждый раз, когда поток переходит из неуправляемого в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="828af-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="828af-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="828af-106">Symptoms</span></span>  
 <span data-ttu-id="828af-107">Приложение, запускающее неуправляемые пользовательские компоненты с помощью модели СОМ и вызова платформы, является причиной недетерминированного нарушения прав доступа в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="828af-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="828af-108">Причина</span><span class="sxs-lookup"><span data-stu-id="828af-108">Cause</span></span>  
 <span data-ttu-id="828af-109">Если приложение выполняет неуправляемые пользовательские компоненты, эти компоненты могут повредить кучу сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="828af-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="828af-110">Это приводит к нарушению прав доступа в среде CLR при попытке сборщика мусора пройти граф объекта.</span><span class="sxs-lookup"><span data-stu-id="828af-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="828af-111">Решение</span><span class="sxs-lookup"><span data-stu-id="828af-111">Resolution</span></span>  
 <span data-ttu-id="828af-112">Включение этого помощника уменьшает время между тем, когда неуправляемый компонент повреждает кучу сборки мусора, и тем, когда происходит нарушение прав доступа принудительным выполнением сборки мусора перед каждой управляемой передачей.</span><span class="sxs-lookup"><span data-stu-id="828af-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="828af-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="828af-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="828af-114">Вызывает сборку мусора каждый раз, когда поток переходит из неуправляемого в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="828af-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="828af-115">Вывод</span><span class="sxs-lookup"><span data-stu-id="828af-115">Output</span></span>  
 <span data-ttu-id="828af-116">Данный MDA не дает результатов.</span><span class="sxs-lookup"><span data-stu-id="828af-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="828af-117">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="828af-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="828af-118">См. также</span><span class="sxs-lookup"><span data-stu-id="828af-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="828af-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="828af-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="828af-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="828af-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="828af-121">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="828af-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
