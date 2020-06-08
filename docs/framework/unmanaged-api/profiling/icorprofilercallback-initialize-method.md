---
title: Метод ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: ea4fc8ab39d616415106150f56f4b7afd5f68237
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500108"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="4411f-102">Метод ICorProfilerCallback::Initialize</span><span class="sxs-lookup"><span data-stu-id="4411f-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="4411f-103">Вызывается для инициализации профилировщика кода при запуске нового приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4411f-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4411f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4411f-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4411f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4411f-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="4411f-106">\[в] указатель на интерфейс [IUnknown](/cpp/atl/iunknown) , который профилировщик должен запрашивать для указателя интерфейса [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4411f-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="4411f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4411f-107">Remarks</span></span>  
 <span data-ttu-id="4411f-108">`Initialize`Вызов является единственной возможностью включать (или отключать) обратные вызовы, которые являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="4411f-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="4411f-109">После включения обратного вызова в `Initialize` вызове он не может быть отключен позже с помощью команды [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="4411f-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="4411f-110">Значение COR_PRF_MONITOR_IMMUTABLE перечисления [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) указывает, какие события являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="4411f-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4411f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4411f-111">Requirements</span></span>  
 <span data-ttu-id="4411f-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4411f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4411f-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4411f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4411f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4411f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4411f-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4411f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4411f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4411f-116">See also</span></span>

- [<span data-ttu-id="4411f-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4411f-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4411f-118">Метод Shutdown</span><span class="sxs-lookup"><span data-stu-id="4411f-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
