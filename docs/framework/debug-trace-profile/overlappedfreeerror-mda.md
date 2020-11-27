---
title: Помощник по отладке управляемого кода overlappedFreeError
description: Ознакомьтесь с помощником по отладке управляемого кода (MDA) Оверлаппедфриеррор в .NET, который может активироваться при нарушениях прав доступа или повреждении кучи, в которой выполняется сбор мусора.
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
ms.openlocfilehash: 1bedb8ad3b9801f0d235371a397c8951ff8723b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254536"
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="2c4d1-103">Помощник по отладке управляемого кода overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="2c4d1-103">overlappedFreeError MDA</span></span>

<span data-ttu-id="2c4d1-104">Помощник по отладке управляемого кода `overlappedFreeError` (MDA) активируется, если метод <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> вызывается до завершения перекрывающейся операции.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-104">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2c4d1-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="2c4d1-105">Symptoms</span></span>  

 <span data-ttu-id="2c4d1-106">Нарушение прав доступа или повреждение кучи сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-106">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2c4d1-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="2c4d1-107">Cause</span></span>  

 <span data-ttu-id="2c4d1-108">Перекрывающаяся структура была освобождена до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-108">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="2c4d1-109">Функция, использующая перекрывающийся указатель, может выполнять запись в структуру позднее, после ее освобождения.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-109">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="2c4d1-110">Это может привести к повреждению кучи, поскольку требуемая область может быть занята другим объектом.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-110">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="2c4d1-111">Этот помощник по отладке управляемого кода может не возвращать ошибку, если перекрывающаяся операция не была успешно запущена.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-111">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2c4d1-112">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2c4d1-112">Resolution</span></span>  

 <span data-ttu-id="2c4d1-113">Прежде чем вызывать метод <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>, убедитесь, что операция ввода-вывода, использующая перекрывающуюся структуру, была завершена.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-113">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2c4d1-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="2c4d1-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="2c4d1-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2c4d1-116">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2c4d1-116">Output</span></span>  

 <span data-ttu-id="2c4d1-117">Ниже приведен пример выходных данных для этого помощника по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2c4d1-117">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="2c4d1-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="2c4d1-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c4d1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2c4d1-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="2c4d1-120">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="2c4d1-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2c4d1-121">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2c4d1-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
