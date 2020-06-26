---
title: gcManagedToUnmanaged MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Гкманажедтаунманажед. Этот MDA может быть активирован из-за преждевременной сборки мусора во время перехода в неуправляемый код.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
ms.openlocfilehash: 76c621a1f2bb780d38228f2a84d4c77441774770
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415918"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="d8d7a-104">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="d8d7a-104">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="d8d7a-105">Помощник по отладке управляемого кода (MDA) `gcManagedToUnmanaged` вызывает сбор мусора каждый раз, когда поток переходит из управляемого в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-105">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d8d7a-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="d8d7a-106">Symptoms</span></span>  
 <span data-ttu-id="d8d7a-107">Неуправляемый пользовательский компонент вызывает нарушение прав доступа при попытке использования управляемого объекта, предоставленного для COM.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-107">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="d8d7a-108">COM-объект выглядит как освобожденный.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-108">The COM object appears to have been released.</span></span> <span data-ttu-id="d8d7a-109">Нарушение прав доступа является недетерминированным.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-109">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d8d7a-110">Причина</span><span class="sxs-lookup"><span data-stu-id="d8d7a-110">Cause</span></span>  
 <span data-ttu-id="d8d7a-111">Если неуправляемый компонент не является ссылкой, правильно учитывающей управляемый COM-объект, среда выполнения может собрать управляемый объект, предоставленный в COM, когда неуправляемый компонент еще содержит ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-111">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="d8d7a-112">Среда выполнения вызывает метод <xref:System.Runtime.InteropServices.Marshal.Release%2A> во время сборки мусора, поэтому если пользовательский компонент использует этот объект до выполнения сборки мусора, то он еще не будет собираться.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-112">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="d8d7a-113">Это источник недетерминированности.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-113">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d8d7a-114">Решение</span><span class="sxs-lookup"><span data-stu-id="d8d7a-114">Resolution</span></span>  
 <span data-ttu-id="d8d7a-115">Включение помощника уменьшает время между тем, когда объект станет доступным для коллекции, и вызовом метода <xref:System.Runtime.InteropServices.Marshal.Release%2A>, помогая отследить, какие неуправляемые компоненты сначала пытаются получить доступ к собранному объекту.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-115">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d8d7a-116">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="d8d7a-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="d8d7a-117">Вызывает сборку мусора каждый раз, когда поток переходит из управляемого в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-117">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d8d7a-118">Вывод</span><span class="sxs-lookup"><span data-stu-id="d8d7a-118">Output</span></span>  
 <span data-ttu-id="d8d7a-119">Данный MDA не дает результатов.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-119">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d8d7a-120">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="d8d7a-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8d7a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d8d7a-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d8d7a-122">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="d8d7a-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d8d7a-123">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="d8d7a-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="d8d7a-124">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="d8d7a-124">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
