---
title: virtualCERCall MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Виртуалцеркалл (MDA), который вызывается, если CER содержит вызов виртуального метода, который не может быть подготовлен автоматически.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
ms.openlocfilehash: fab0686b1c7d2fbb1485f6e4b82d008495a553cd
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803564"
---
# <a name="virtualcercall-mda"></a><span data-ttu-id="2c63b-103">virtualCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="2c63b-103">virtualCERCall MDA</span></span>
<span data-ttu-id="2c63b-104">Помощник по отладке управляемого кода (MDA) `virtualCERCall` активируется как предупреждение, указывающее на то, что точка вызова в графе вызовов для области ограниченного выполнения (CER) относится к виртуальному целевому объекту, то есть к виртуальному вызову неконечного виртуального метода или к вызову с помощью интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2c63b-104">The `virtualCERCall` managed debugging assistant (MDA) is activated as a warning indicating that a call site within a constrained execution region (CER) call graph refers to a virtual target, that is, a virtual call to a non-final virtual method or a call using an interface.</span></span> <span data-ttu-id="2c63b-105">Среда CLR не может спрогнозировать конечный метод этих вызовов только на основании промежуточного языка и анализа метаданных.</span><span class="sxs-lookup"><span data-stu-id="2c63b-105">The common language runtime (CLR) cannot predict the destination method of these calls from the intermediate language and metadata analysis alone.</span></span> <span data-ttu-id="2c63b-106">В результате дерево вызовов невозможно подготовить как часть графа CER и прерывания потока в этом поддереве невозможно блокировать автоматически.</span><span class="sxs-lookup"><span data-stu-id="2c63b-106">As a result, the call tree cannot be prepared as part of the CER graph and thread aborts in that subtree cannot be automatically blocked.</span></span> <span data-ttu-id="2c63b-107">Этот помощник по отладке управляемого кода предупреждает о случаях, когда CER требуется расширить с помощью явных вызовов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>, если дополнительные сведения, требуемые для вычисления целевого объекта вызова, известны во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2c63b-107">This MDA warns of cases where a CER might need to be extended by using explicit calls to the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method once the additional information required to compute the call target is known at run time.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2c63b-108">Симптомы</span><span class="sxs-lookup"><span data-stu-id="2c63b-108">Symptoms</span></span>  
 <span data-ttu-id="2c63b-109">Области CER, которые не выполняются при прерывании потока или при выгрузке домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2c63b-109">CERs that do not run when a thread is aborted or an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2c63b-110">Причина</span><span class="sxs-lookup"><span data-stu-id="2c63b-110">Cause</span></span>  
 <span data-ttu-id="2c63b-111">CER содержит вызов виртуального метода, который не удается подготовить автоматически.</span><span class="sxs-lookup"><span data-stu-id="2c63b-111">A CER contains a call to a virtual method that cannot be prepared automatically.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2c63b-112">Решение</span><span class="sxs-lookup"><span data-stu-id="2c63b-112">Resolution</span></span>  
 <span data-ttu-id="2c63b-113">Следует вызвать <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> для виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="2c63b-113">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> for the virtual method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2c63b-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="2c63b-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="2c63b-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="2c63b-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2c63b-116">Вывод</span><span class="sxs-lookup"><span data-stu-id="2c63b-116">Output</span></span>  
  
```output
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a><span data-ttu-id="2c63b-117">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="2c63b-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="2c63b-118">Пример</span><span class="sxs-lookup"><span data-stu-id="2c63b-118">Example</span></span>  
  
```csharp
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c63b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2c63b-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="2c63b-120">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="2c63b-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2c63b-121">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2c63b-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
