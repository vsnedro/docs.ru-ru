---
title: Метод ICorProfilerCallback::ClassLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: fbdc9345c8364f33ac69da452dd91155fd5eede9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700279"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="97a16-102">Метод ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="97a16-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>

<span data-ttu-id="97a16-103">Уведомляет профилировщик о том, что класс загружается.</span><span class="sxs-lookup"><span data-stu-id="97a16-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97a16-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97a16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97a16-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="97a16-106">\[в] определяет класс, который загружается.</span><span class="sxs-lookup"><span data-stu-id="97a16-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="97a16-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="97a16-107">Remarks</span></span>  

 <span data-ttu-id="97a16-108">Значение недопустимо `classId` для информационного запроса, пока не будет вызван метод [ICorProfilerCallback:: класслоадфинишед](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="97a16-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97a16-109">Требования</span><span class="sxs-lookup"><span data-stu-id="97a16-109">Requirements</span></span>  

 <span data-ttu-id="97a16-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a16-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97a16-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97a16-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97a16-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97a16-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97a16-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97a16-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a16-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="97a16-114">See also</span></span>

- [<span data-ttu-id="97a16-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="97a16-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
