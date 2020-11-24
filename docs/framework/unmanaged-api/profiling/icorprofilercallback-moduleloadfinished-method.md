---
title: Метод ICorProfilerCallback::ModuleLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 5a29507ca56cac4ab800845e3a88706dc7a25379
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683996"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="5fee2-102">Метод ICorProfilerCallback::ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="5fee2-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>

<span data-ttu-id="5fee2-103">Уведомляет профилировщик о завершении загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="5fee2-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fee2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fee2-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fee2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fee2-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="5fee2-106">окне Идентификатор модуля, загрузка которого завершена.</span><span class="sxs-lookup"><span data-stu-id="5fee2-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="5fee2-107">окне Значение HRESULT, указывающее, успешно ли загружен модуль.</span><span class="sxs-lookup"><span data-stu-id="5fee2-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fee2-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5fee2-108">Remarks</span></span>  

 <span data-ttu-id="5fee2-109">Значение недопустимо `moduleId` для информационного запроса до `ModuleLoadFinished` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="5fee2-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="5fee2-110">Некоторые части загрузки модуля могут продолжаться после `ModuleLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5fee2-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="5fee2-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="5fee2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="5fee2-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть загрузки модуля завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="5fee2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fee2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5fee2-113">Requirements</span></span>  

 <span data-ttu-id="5fee2-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fee2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fee2-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fee2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fee2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fee2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fee2-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fee2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fee2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5fee2-118">See also</span></span>

- [<span data-ttu-id="5fee2-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5fee2-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5fee2-120">Метод ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="5fee2-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
