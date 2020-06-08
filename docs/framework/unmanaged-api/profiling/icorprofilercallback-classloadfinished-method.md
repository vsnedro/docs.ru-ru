---
title: Метод ICorProfilerCallback::ClassLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: 4be2a50664b001e865b5ecdd9aabe8ba727b8c26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500394"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="e8ff2-102">Метод ICorProfilerCallback::ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="e8ff2-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="e8ff2-103">Уведомляет профилировщик о том, что загрузка класса завершена.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ff2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8ff2-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8ff2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8ff2-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="e8ff2-106">\[в] определяет класс, который был загружен.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="e8ff2-107">\[in] значение HRESULT, указывающее, успешно ли загружен класс.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8ff2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8ff2-108">Remarks</span></span>  
 <span data-ttu-id="e8ff2-109">Значение недопустимо `classId` для информационного запроса до `ClassLoadFinished` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="e8ff2-110">Некоторые части загрузки класса могут продолжаться после `ClassLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="e8ff2-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e8ff2-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть загрузки класса завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="e8ff2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ff2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e8ff2-113">Requirements</span></span>  
 <span data-ttu-id="e8ff2-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ff2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8ff2-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8ff2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8ff2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8ff2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8ff2-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ff2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ff2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e8ff2-118">See also</span></span>

- [<span data-ttu-id="e8ff2-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e8ff2-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e8ff2-120">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="e8ff2-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
