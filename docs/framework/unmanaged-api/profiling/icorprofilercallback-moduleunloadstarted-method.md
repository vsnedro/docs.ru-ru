---
title: Метод ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: 12d5f7e073337af6034b8f313a2e0161620a65ea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720962"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="afb6d-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="afb6d-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>

<span data-ttu-id="afb6d-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="afb6d-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afb6d-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="afb6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="afb6d-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="afb6d-106">окне Идентификатор выгружается модуля.</span><span class="sxs-lookup"><span data-stu-id="afb6d-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afb6d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="afb6d-107">Remarks</span></span>  

 <span data-ttu-id="afb6d-108">Значение недопустимо `moduleId` для информационного запроса после `ModuleUnloadStarted` возврата метода — это последний шанс профилировщика получить сведения об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="afb6d-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afb6d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="afb6d-109">Requirements</span></span>  

 <span data-ttu-id="afb6d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afb6d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afb6d-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="afb6d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="afb6d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afb6d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afb6d-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afb6d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb6d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afb6d-114">See also</span></span>

- [<span data-ttu-id="afb6d-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="afb6d-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="afb6d-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="afb6d-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
