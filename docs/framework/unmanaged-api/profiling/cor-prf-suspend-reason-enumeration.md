---
title: Перечисление COR_PRF_SUSPEND_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: f7d76c72ed5db95425f5b1fa2db5e4346983daa4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696678"
---
# <a name="cor_prf_suspend_reason-enumeration"></a><span data-ttu-id="27675-102">Перечисление COR_PRF_SUSPEND_REASON</span><span class="sxs-lookup"><span data-stu-id="27675-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>

<span data-ttu-id="27675-103">Указывает причину приостановки выполнения.</span><span class="sxs-lookup"><span data-stu-id="27675-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27675-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27675-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="27675-105">Члены</span><span class="sxs-lookup"><span data-stu-id="27675-105">Members</span></span>  
  
|<span data-ttu-id="27675-106">Член</span><span class="sxs-lookup"><span data-stu-id="27675-106">Member</span></span>|<span data-ttu-id="27675-107">Описание</span><span class="sxs-lookup"><span data-stu-id="27675-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="27675-108">Среда выполнения приостановлена по неизвестной причине.</span><span class="sxs-lookup"><span data-stu-id="27675-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="27675-109">Среда выполнения приостановлена для обслуживания запроса на сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="27675-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="27675-110">Обратные вызовы, связанные со сборкой мусора, происходят между обратными вызовами [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) и [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="27675-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="27675-111">Среда выполнения приостановлена, чтобы `AppDomain` можно было завершить работу.</span><span class="sxs-lookup"><span data-stu-id="27675-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="27675-112">Пока среда выполнения приостановлена, среда выполнения определит, какие потоки находятся в `AppDomain` , и задаст их в случае прерывания работы.</span><span class="sxs-lookup"><span data-stu-id="27675-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="27675-113">`AppDomain`Во время этой приостановки не существует специальных обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="27675-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="27675-114">Среда выполнения приостановлена, поэтому может произойти пошаговое выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="27675-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="27675-115">Шаг с текстом выполняется, только если JIT-компилятор активен с включенным шагом в коде.</span><span class="sxs-lookup"><span data-stu-id="27675-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="27675-116">Обратные вызовы с пошаговым выполнением кода происходят между `ICorProfilerCallback::RuntimeSuspendFinished` `ICorProfilerCallback::RuntimeResumeStarted` ответами и.</span><span class="sxs-lookup"><span data-stu-id="27675-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="27675-117">**Примечание.**  JIT-компилятор CLR не выполняет функции в .NET Framework версии 2,0, поэтому это значение не используется в 2,0.</span><span class="sxs-lookup"><span data-stu-id="27675-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="27675-118">Среда выполнения приостановлена, поэтому она может завершить работу.</span><span class="sxs-lookup"><span data-stu-id="27675-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="27675-119">Чтобы завершить операцию, необходимо приостановить все потоки.</span><span class="sxs-lookup"><span data-stu-id="27675-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="27675-120">Среда выполнения приостанавливается для внутрипроцессного процесса отладки.</span><span class="sxs-lookup"><span data-stu-id="27675-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="27675-121">Среда выполнения приостановлена для подготовки к сбору мусора.</span><span class="sxs-lookup"><span data-stu-id="27675-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="27675-122">Среда выполнения приостанавливается для повторной компиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="27675-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27675-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="27675-123">Remarks</span></span>  

 <span data-ttu-id="27675-124">Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения, после чего они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="27675-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="27675-125">Это также относится к новым потокам, которые вводят среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="27675-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="27675-126">Все потоки в среде выполнения либо приостанавливаются немедленно, если они находятся в коде для преобразования, либо запрашивается их приостановка, когда они достигают кода источника.</span><span class="sxs-lookup"><span data-stu-id="27675-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27675-127">Требования</span><span class="sxs-lookup"><span data-stu-id="27675-127">Requirements</span></span>  

 <span data-ttu-id="27675-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27675-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27675-129">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27675-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27675-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27675-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27675-131">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27675-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27675-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="27675-132">See also</span></span>

- [<span data-ttu-id="27675-133">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="27675-133">Profiling Enumerations</span></span>](profiling-enumerations.md)
