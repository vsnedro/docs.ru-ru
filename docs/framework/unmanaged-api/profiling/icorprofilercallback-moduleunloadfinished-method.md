---
title: Метод ICorProfilerCallback::ModuleUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: fd35f47c004d1ffb235cefe1cd2a1eb2c1fffaef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503319"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="89e28-102">Метод ICorProfilerCallback::ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="89e28-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="89e28-103">Уведомляет профилировщик о завершении выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="89e28-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89e28-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89e28-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="89e28-106">окне Идентификатор выгруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="89e28-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="89e28-107">окне Значение HRESULT, указывающее, успешно ли выгружен модуль.</span><span class="sxs-lookup"><span data-stu-id="89e28-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89e28-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="89e28-108">Remarks</span></span>  
 <span data-ttu-id="89e28-109">Значение недопустимо `moduleId` для информационного запроса после возврата метода [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="89e28-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="89e28-110">Некоторые части выгрузки класса могут продолжаться после `ModuleUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="89e28-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="89e28-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="89e28-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="89e28-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть выгрузки модуля успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="89e28-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e28-113">Требования</span><span class="sxs-lookup"><span data-stu-id="89e28-113">Requirements</span></span>  
 <span data-ttu-id="89e28-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e28-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e28-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89e28-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89e28-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89e28-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89e28-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e28-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e28-118">См. также</span><span class="sxs-lookup"><span data-stu-id="89e28-118">See also</span></span>

- [<span data-ttu-id="89e28-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="89e28-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
