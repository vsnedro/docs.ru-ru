---
title: Метод ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500381"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="fef43-102">Метод ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="fef43-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="fef43-103">Уведомляет профилировщик о завершении выгрузки класса.</span><span class="sxs-lookup"><span data-stu-id="fef43-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fef43-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fef43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fef43-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="fef43-106">\[в] определяет класс, который был выгружен.</span><span class="sxs-lookup"><span data-stu-id="fef43-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="fef43-107">\[in] значение HRESULT, указывающее, успешно ли выгружен класс.</span><span class="sxs-lookup"><span data-stu-id="fef43-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fef43-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="fef43-108">Remarks</span></span>  
 <span data-ttu-id="fef43-109">Некоторые части выгрузки класса могут продолжаться после `ClassUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="fef43-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="fef43-110">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="fef43-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="fef43-111">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть выгрузки класса успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="fef43-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fef43-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fef43-112">Requirements</span></span>  
 <span data-ttu-id="fef43-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef43-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef43-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fef43-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fef43-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fef43-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fef43-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fef43-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef43-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fef43-117">See also</span></span>

- [<span data-ttu-id="fef43-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fef43-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="fef43-119">Метод ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="fef43-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
