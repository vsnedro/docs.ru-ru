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
ms.openlocfilehash: 61fbdbf0d3941aa3e876748ae4d76cd7ad0c0977
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244227"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="d9ad0-104">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="d9ad0-104">gcUnmanagedToManaged MDA</span></span>

<span data-ttu-id="d9ad0-105">Помощник по отладке управляемого кода (MDA) `gcUnmanagedToManaged` вызывает сбор мусора каждый раз, когда поток переходит из неуправляемого в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d9ad0-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="d9ad0-106">Symptoms</span></span>  

 <span data-ttu-id="d9ad0-107">Приложение, запускающее неуправляемые пользовательские компоненты с помощью модели СОМ и вызова платформы, является причиной недетерминированного нарушения прав доступа в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d9ad0-108">Причина:</span><span class="sxs-lookup"><span data-stu-id="d9ad0-108">Cause</span></span>  

 <span data-ttu-id="d9ad0-109">Если приложение выполняет неуправляемые пользовательские компоненты, эти компоненты могут повредить кучу сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="d9ad0-110">Это приводит к нарушению прав доступа в среде CLR при попытке сборщика мусора пройти граф объекта.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d9ad0-111">Разрешение</span><span class="sxs-lookup"><span data-stu-id="d9ad0-111">Resolution</span></span>  

 <span data-ttu-id="d9ad0-112">Включение этого помощника уменьшает время между тем, когда неуправляемый компонент повреждает кучу сборки мусора, и тем, когда происходит нарушение прав доступа принудительным выполнением сборки мусора перед каждой управляемой передачей.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d9ad0-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="d9ad0-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="d9ad0-114">Вызывает сборку мусора каждый раз, когда поток переходит из неуправляемого в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d9ad0-115">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d9ad0-115">Output</span></span>  

 <span data-ttu-id="d9ad0-116">Данный MDA не дает результатов.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d9ad0-117">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d9ad0-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9ad0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d9ad0-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d9ad0-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="d9ad0-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d9ad0-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="d9ad0-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="d9ad0-121">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="d9ad0-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
