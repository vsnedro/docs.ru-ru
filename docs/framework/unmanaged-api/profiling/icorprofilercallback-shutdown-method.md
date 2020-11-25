---
title: Метод ICorProfilerCallback::Shutdown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 9761eb5085a77279c4d07d39946a5ad1453ecaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717277"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="e3d07-102">Метод ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="e3d07-102">ICorProfilerCallback::Shutdown Method</span></span>

<span data-ttu-id="e3d07-103">Уведомляет профилировщик о том, что приложение завершает работу.</span><span class="sxs-lookup"><span data-stu-id="e3d07-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3d07-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e3d07-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3d07-105">Remarks</span></span>  

 <span data-ttu-id="e3d07-106">Код профилировщика не может безопасно вызывать методы интерфейса [ICorProfilerInfo](icorprofilerinfo-interface.md) после `Shutdown` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="e3d07-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="e3d07-107">Все вызовы `ICorProfilerInfo` методов приводят к неопределенному поведению после `Shutdown` возврата метода.</span><span class="sxs-lookup"><span data-stu-id="e3d07-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="e3d07-108">Некоторые неизменяемые события по-прежнему могут возникать после завершения работы. Профилировщик должен немедленно возвращаться к моменту, когда это происходит.</span><span class="sxs-lookup"><span data-stu-id="e3d07-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="e3d07-109">`Shutdown`Метод будет вызываться только в том случае, если управляемое приложение, профилирование которого запускается как управляемый код (т. е. исходный кадр в стеке процессов является управляемым).</span><span class="sxs-lookup"><span data-stu-id="e3d07-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="e3d07-110">Если приложение запущено в виде неуправляемого кода, но позднее перейдет в управляемый код, то создание экземпляра среды CLR `Shutdown` не будет вызвано.</span><span class="sxs-lookup"><span data-stu-id="e3d07-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="e3d07-111">В таких случаях профилировщик должен включать в свою библиотеку `DllMain` подпрограммы, которая использует значение DLL_PROCESS_DETACH для высвобождения любых ресурсов и выполнения очистки данных, таких как сброс трассировок на диск и т. д.</span><span class="sxs-lookup"><span data-stu-id="e3d07-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="e3d07-112">Как правило, профилировщик должен справляться с непредвиденным завершением работы.</span><span class="sxs-lookup"><span data-stu-id="e3d07-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="e3d07-113">Например, процесс может быть остановлен `TerminateProcess` методом Win32's (объявлен в винбасе. h).</span><span class="sxs-lookup"><span data-stu-id="e3d07-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="e3d07-114">В других случаях среда CLR остановит определенные управляемые потоки (фоновые потоки), не создавая для них сообщения с неупорядоченным уничтожением.</span><span class="sxs-lookup"><span data-stu-id="e3d07-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3d07-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e3d07-115">Requirements</span></span>  

 <span data-ttu-id="e3d07-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3d07-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3d07-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3d07-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3d07-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3d07-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3d07-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d07-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d07-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e3d07-120">See also</span></span>

- [<span data-ttu-id="e3d07-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e3d07-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e3d07-122">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="e3d07-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
