---
title: dangerousThreadingAPI MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Данжерауссреадингапи (MDA), который активируется при вызове Thread. Suspend в потоке, отличном от текущего потока.
ms.date: 03/30/2017
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
ms.openlocfilehash: 9069ccb6f106c83db94f88bc464bc0888d28586c
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416009"
---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="c9666-103">dangerousThreadingAPI MDA</span><span class="sxs-lookup"><span data-stu-id="c9666-103">dangerousThreadingAPI MDA</span></span>
<span data-ttu-id="c9666-104">Помощник по отладке управляемого кода `dangerousThreadingAPI` (MDA) активируется, если метод <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> вызывается не для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="c9666-104">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c9666-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="c9666-105">Symptoms</span></span>  
 <span data-ttu-id="c9666-106">Приложение не отвечает или зависает на неопределенное время.</span><span class="sxs-lookup"><span data-stu-id="c9666-106">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="c9666-107">Данные системы или приложения могут остаться в непредсказуемом состоянии на какое-то время или даже после завершения работы приложения.</span><span class="sxs-lookup"><span data-stu-id="c9666-107">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="c9666-108">Некоторые операции не завершаются должным образом.</span><span class="sxs-lookup"><span data-stu-id="c9666-108">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="c9666-109">Из-за случайного характера возникновения этой проблемы ее симптомы могут быть самыми разными.</span><span class="sxs-lookup"><span data-stu-id="c9666-109">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c9666-110">Причина</span><span class="sxs-lookup"><span data-stu-id="c9666-110">Cause</span></span>  
 <span data-ttu-id="c9666-111">Поток асинхронно приостанавливается другим потоком, использующим метод <xref:System.Threading.Thread.Suspend%2A>.</span><span class="sxs-lookup"><span data-stu-id="c9666-111">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="c9666-112">Определить, безопасно ли приостанавливать другой поток, который в текущий момент времени может выполнять другие операции, невозможно.</span><span class="sxs-lookup"><span data-stu-id="c9666-112">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="c9666-113">Приостановка потока может привести к повреждению данных или нарушению инвариантов.</span><span class="sxs-lookup"><span data-stu-id="c9666-113">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="c9666-114">Если поток приостанавливается и впоследствии не возобновляется с помощью метода <xref:System.Threading.Thread.Resume%2A>, приложение может зависнуть на неопределенное время, что может привести к повреждению его данных.</span><span class="sxs-lookup"><span data-stu-id="c9666-114">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="c9666-115">Эти методы помечены как устаревшие.</span><span class="sxs-lookup"><span data-stu-id="c9666-115">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="c9666-116">Если целевой поток удерживает примитивы синхронизации, они остаются в этом состоянии на протяжении всего времени приостановки.</span><span class="sxs-lookup"><span data-stu-id="c9666-116">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="c9666-117">Это может привести к взаимоблокировкам в тех случаях, когда другой поток, например поток, выполняющий <xref:System.Threading.Thread.Suspend%2A>, пытается получить блокировку примитива.</span><span class="sxs-lookup"><span data-stu-id="c9666-117">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="c9666-118">В этой ситуации проблема проявляется в виде взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="c9666-118">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c9666-119">Решение</span><span class="sxs-lookup"><span data-stu-id="c9666-119">Resolution</span></span>  
 <span data-ttu-id="c9666-120">По возможности не используйте в коде методы <xref:System.Threading.Thread.Suspend%2A> и <xref:System.Threading.Thread.Resume%2A>.</span><span class="sxs-lookup"><span data-stu-id="c9666-120">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="c9666-121">Чтобы обеспечить взаимодействие между потоками, используйте примитивы синхронизации, например <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> или оператор `lock` C#.</span><span class="sxs-lookup"><span data-stu-id="c9666-121">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="c9666-122">Если эти методы все же необходимо использовать, постарайтесь свести к минимуму продолжительность приостановки потока и объем кода, выполняемого в это время.</span><span class="sxs-lookup"><span data-stu-id="c9666-122">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c9666-123">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="c9666-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="c9666-124">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="c9666-124">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="c9666-125">Он только сообщает сведения о небезопасных потоковых операциях.</span><span class="sxs-lookup"><span data-stu-id="c9666-125">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c9666-126">Вывод</span><span class="sxs-lookup"><span data-stu-id="c9666-126">Output</span></span>  
 <span data-ttu-id="c9666-127">Этот помощник идентифицирует небезопасный потоковый метод, который стал причиной его активации.</span><span class="sxs-lookup"><span data-stu-id="c9666-127">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c9666-128">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="c9666-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="c9666-129">Пример</span><span class="sxs-lookup"><span data-stu-id="c9666-129">Example</span></span>  
 <span data-ttu-id="c9666-130">В следующем примере кода демонстрируется вызов метода <xref:System.Threading.Thread.Suspend%2A>, в результате которого активируется помощник `dangerousThreadingAPI`.</span><span class="sxs-lookup"><span data-stu-id="c9666-130">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
```csharp
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9666-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c9666-131">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="c9666-132">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="c9666-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c9666-133">Оператор lock</span><span class="sxs-lookup"><span data-stu-id="c9666-133">lock Statement</span></span>](../../csharp/language-reference/keywords/lock-statement.md)
