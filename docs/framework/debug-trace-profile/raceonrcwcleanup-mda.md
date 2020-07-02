---
title: Помощник по отладке управляемого кода raceOnRCWCleanup
description: Ознакомьтесь с помощником по отладке управляемого кода Рацеонрквклеануп (MDA), который активируется, если RCW используется в другом потоке или в стеке освобождения потоков в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: e86ef96bebb648c7927ae5fec8b68fc4429b268b
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803655"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="f90f9-103">Помощник по отладке управляемого кода raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="f90f9-103">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="f90f9-104">Помощник по отладке управляемого кода (MDA) `raceOnRCWCleanup` активируется, когда среда CLR обнаруживает, что используется [вызываемая оболочка времени выполнения](../../standard/native-interop/runtime-callable-wrapper.md) (RCW), когда выполняется вызов освобождения с помощью команды, такой как метод <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f90f9-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f90f9-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="f90f9-105">Symptoms</span></span>  
 <span data-ttu-id="f90f9-106">Нарушение прав доступа или повреждение памяти во время или после освобождения RCW с помощью метода <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> или аналогичным способом.</span><span class="sxs-lookup"><span data-stu-id="f90f9-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f90f9-107">Причина</span><span class="sxs-lookup"><span data-stu-id="f90f9-107">Cause</span></span>  
 <span data-ttu-id="f90f9-108">RCW используется в другом потоке или в стеке высвобождения потоков.</span><span class="sxs-lookup"><span data-stu-id="f90f9-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="f90f9-109">RCW, которая используется, не может быть освобождена.</span><span class="sxs-lookup"><span data-stu-id="f90f9-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f90f9-110">Решение</span><span class="sxs-lookup"><span data-stu-id="f90f9-110">Resolution</span></span>  
 <span data-ttu-id="f90f9-111">Не освобождайте RCW, которая может использоваться в текущем или в других потоках.</span><span class="sxs-lookup"><span data-stu-id="f90f9-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f90f9-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="f90f9-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="f90f9-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="f90f9-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f90f9-114">Вывод</span><span class="sxs-lookup"><span data-stu-id="f90f9-114">Output</span></span>  
 <span data-ttu-id="f90f9-115">Сообщение, описывающее ошибку.</span><span class="sxs-lookup"><span data-stu-id="f90f9-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f90f9-116">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="f90f9-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f90f9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f90f9-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f90f9-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="f90f9-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f90f9-119">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f90f9-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
