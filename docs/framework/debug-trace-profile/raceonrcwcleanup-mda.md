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
ms.openlocfilehash: 393c5ea44108445a9a1a9d16e7d1d192eced5740
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271451"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="4c9bd-103">Помощник по отладке управляемого кода raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="4c9bd-103">raceOnRCWCleanup MDA</span></span>

<span data-ttu-id="4c9bd-104">Помощник по отладке управляемого кода (MDA) `raceOnRCWCleanup` активируется, когда среда CLR обнаруживает, что используется [вызываемая оболочка времени выполнения](../../standard/native-interop/runtime-callable-wrapper.md) (RCW), когда выполняется вызов освобождения с помощью команды, такой как метод <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4c9bd-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="4c9bd-105">Symptoms</span></span>  

 <span data-ttu-id="4c9bd-106">Нарушение прав доступа или повреждение памяти во время или после освобождения RCW с помощью метода <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> или аналогичным способом.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4c9bd-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="4c9bd-107">Cause</span></span>  

 <span data-ttu-id="4c9bd-108">RCW используется в другом потоке или в стеке высвобождения потоков.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="4c9bd-109">RCW, которая используется, не может быть освобождена.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4c9bd-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="4c9bd-110">Resolution</span></span>  

 <span data-ttu-id="4c9bd-111">Не освобождайте RCW, которая может использоваться в текущем или в других потоках.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4c9bd-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="4c9bd-112">Effect on the Runtime</span></span>  

 <span data-ttu-id="4c9bd-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4c9bd-114">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4c9bd-114">Output</span></span>  

 <span data-ttu-id="4c9bd-115">Сообщение, описывающее ошибку.</span><span class="sxs-lookup"><span data-stu-id="4c9bd-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4c9bd-116">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4c9bd-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c9bd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4c9bd-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4c9bd-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="4c9bd-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4c9bd-119">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="4c9bd-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
