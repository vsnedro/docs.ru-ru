---
title: Метод ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: fd41463af0acac1bbe1a3d4515350905b6784f79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685347"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="ec7a4-102">Метод ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="ec7a4-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>

<span data-ttu-id="ec7a4-103">Уведомляет профилировщик о том, что загрузка сборки завершена.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec7a4-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec7a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec7a4-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="ec7a4-106">\[в] определяет сборку, которая была загружена.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="ec7a4-107">\[in] значение HRESULT, указывающее, успешно ли завершена загрузка сборки.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec7a4-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ec7a4-108">Remarks</span></span>  

 <span data-ttu-id="ec7a4-109">Значение недопустимо `assemblyId` для информационного запроса до `AssemblyLoadFinished` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="ec7a4-110">Некоторые части загрузки сборки могут продолжаться после `AssemblyLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="ec7a4-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ec7a4-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть загрузки сборки завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="ec7a4-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec7a4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ec7a4-113">Requirements</span></span>  

 <span data-ttu-id="ec7a4-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec7a4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec7a4-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec7a4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec7a4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec7a4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec7a4-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec7a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7a4-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec7a4-118">See also</span></span>

- [<span data-ttu-id="ec7a4-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ec7a4-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
