---
title: illegalPrepareConstrainedRegion MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Иллегалпрепареконстраинедрегион, который вызывается, если за вызовом PrepareConstrainedRegions не следует инструкция Try.
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: d6a0d1d95840ebd735806c5547730ae9e0b2aace
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051289"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="90119-103">illegalPrepareConstrainedRegion MDA</span><span class="sxs-lookup"><span data-stu-id="90119-103">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="90119-104">Помощник по отладке управляемого кода (MDA) `illegalPrepareConstrainedRegion` запускается, если сразу же после вызова метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> не следует инструкция `try` обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="90119-104">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="90119-105">Это ограничение используется на уровне MSIL, поэтому между вызовом и `try` можно размещать текст, не приводящий к созданию кода, например комментарии.</span><span class="sxs-lookup"><span data-stu-id="90119-105">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="90119-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="90119-106">Symptoms</span></span>  
 <span data-ttu-id="90119-107">Область ограниченного выполнения, которая никогда не рассматривается в виде такой области, но представляет собой простой блок обработки исключений (`finally` или `catch`).</span><span class="sxs-lookup"><span data-stu-id="90119-107">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="90119-108">Поэтому эта область не запускается в случае нехватки памяти или прерывания потока.</span><span class="sxs-lookup"><span data-stu-id="90119-108">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="90119-109">Причина:</span><span class="sxs-lookup"><span data-stu-id="90119-109">Cause</span></span>  
 <span data-ttu-id="90119-110">Вы не следуете шаблону подготовки для области ограниченного выполнения.</span><span class="sxs-lookup"><span data-stu-id="90119-110">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="90119-111">Это ошибка.</span><span class="sxs-lookup"><span data-stu-id="90119-111">This is an error event.</span></span> <span data-ttu-id="90119-112"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>Вызов метода, используемый для пометки обработчиков исключений как знакомого CER в `catch` / `finally` / `fault` / `filter` блоках, должен использоваться непосредственно перед `try` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="90119-112">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="90119-113">Решение</span><span class="sxs-lookup"><span data-stu-id="90119-113">Resolution</span></span>  
 <span data-ttu-id="90119-114">Убедитесь, что вызов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> выполняется непосредственно перед инструкцией `try`.</span><span class="sxs-lookup"><span data-stu-id="90119-114">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="90119-115">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="90119-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="90119-116">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="90119-116">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="90119-117">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="90119-117">Output</span></span>  
 <span data-ttu-id="90119-118">Помощник по отладке управляемого кода отображает имя метода, вызывающего метод <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, смещение MSIL и сообщение о том, что вызов метода выполняется не перед началом блока try.</span><span class="sxs-lookup"><span data-stu-id="90119-118">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="90119-119">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="90119-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="90119-120">Пример</span><span class="sxs-lookup"><span data-stu-id="90119-120">Example</span></span>  
 <span data-ttu-id="90119-121">В следующем примере кода показан шаблон, который запускает этот помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="90119-121">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="90119-122">См. также</span><span class="sxs-lookup"><span data-stu-id="90119-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="90119-123">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="90119-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="90119-124">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="90119-124">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
