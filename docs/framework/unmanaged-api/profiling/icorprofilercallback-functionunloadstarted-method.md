---
title: Метод ICorProfilerCallback::FunctionUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: bab8d446347646081cee635035e954da58c3550c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733884"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="b59ec-102">Метод ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="b59ec-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="b59ec-103">Уведомляет профилировщик о запуске среды выполнения для выгрузки функции.</span><span class="sxs-lookup"><span data-stu-id="b59ec-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b59ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b59ec-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="b59ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b59ec-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="b59ec-106">\[in] идентификатор выгрузки функции.</span><span class="sxs-lookup"><span data-stu-id="b59ec-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="b59ec-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b59ec-107">Remarks</span></span>  

 <span data-ttu-id="b59ec-108">Значение `functionId` параметра больше не является допустимым после возврата этим методом вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="b59ec-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b59ec-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b59ec-109">Requirements</span></span>  

 <span data-ttu-id="b59ec-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b59ec-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b59ec-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b59ec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b59ec-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b59ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b59ec-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b59ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b59ec-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b59ec-114">See also</span></span>

- [<span data-ttu-id="b59ec-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b59ec-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
