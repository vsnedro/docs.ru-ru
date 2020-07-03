---
title: Основные и фоновые потоки
description: Вы можете определить или изменить то, является ли поток фоновым или основным, с помощью свойства Thread.IsBackground в .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 6cb7a92851728e16f4a317d6c24d072acee72a94
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769045"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="d748b-103">Основные и фоновые потоки</span><span class="sxs-lookup"><span data-stu-id="d748b-103">Foreground and Background Threads</span></span>
<span data-ttu-id="d748b-104">Управляемый поток может быть основным или фоновым.</span><span class="sxs-lookup"><span data-stu-id="d748b-104">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="d748b-105">Фоновые потоки отличаются от основных только в одном аспекте: фоновый поток не поддерживает работу управляемой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d748b-105">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="d748b-106">После того, как в управляемом процессе (где управляемой сборкой является файл EXE) остановятся все основные потоки, система принудительно останавливает все фоновые потоки и завершает работу процесса.</span><span class="sxs-lookup"><span data-stu-id="d748b-106">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d748b-107">Когда в среде выполнения останавливается фоновый поток из-за завершения работы процесса, исключение в потоке не возникает.</span><span class="sxs-lookup"><span data-stu-id="d748b-107">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="d748b-108">Но если потоки останавливаются из-за выгрузки домена приложения в методе <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>, во всех основных и фоновых потоках создается исключение <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="d748b-108">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="d748b-109">Свойство <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> позволяет определить, является ли поток основным или фоновым, а также изменить его статус.</span><span class="sxs-lookup"><span data-stu-id="d748b-109">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="d748b-110">Поток можно в любой момент сделать фоновым, задав в нем для свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d748b-110">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d748b-111">Основное или фоновое состояние потока не влияет на поведение необработанного исключения в потоке.</span><span class="sxs-lookup"><span data-stu-id="d748b-111">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="d748b-112">На платформе .NET Framework версии 2.0 необработанное исключение в основном или фоновом потоке приведет к завершению работы приложения.</span><span class="sxs-lookup"><span data-stu-id="d748b-112">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="d748b-113">См. также [Исключения в управляемых потоках](exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="d748b-113">See [Exceptions in Managed Threads](exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="d748b-114">Потоки, входящие в пул управляемых потоков (то есть потоки, в которых для свойства <xref:System.Threading.Thread.IsThreadPoolThread%2A> задано значение `true`), считаются фоновыми потоками.</span><span class="sxs-lookup"><span data-stu-id="d748b-114">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="d748b-115">Все потоки, которые включаются в управляемую среду выполнения из неуправляемого кода, помечаются как фоновые потоки.</span><span class="sxs-lookup"><span data-stu-id="d748b-115">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="d748b-116">Все потоки, созданные путем создания и запуска нового объекта <xref:System.Threading.Thread>, по умолчанию становятся основными потоками.</span><span class="sxs-lookup"><span data-stu-id="d748b-116">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="d748b-117">Если у вас есть поток, который отслеживает некоторое действие, например подключение через сокет, установите для его свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`, чтобы этот поток не мешал завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="d748b-117">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d748b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d748b-118">See also</span></span>

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
