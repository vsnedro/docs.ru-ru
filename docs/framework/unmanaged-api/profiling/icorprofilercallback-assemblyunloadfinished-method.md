---
title: Метод ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: d00e67d29921edc6b7487ceeb12aaa9e9f9bd0ac
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500420"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="2732d-102">Метод ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="2732d-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="2732d-103">Уведомляет профилировщик о том, что сборка была выгружена.</span><span class="sxs-lookup"><span data-stu-id="2732d-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2732d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2732d-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2732d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2732d-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="2732d-106">\[в] определяет сборку, которая выгружается.</span><span class="sxs-lookup"><span data-stu-id="2732d-106">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="2732d-107">\[in] значение HRESULT, указывающее, успешно ли выгружена сборка.</span><span class="sxs-lookup"><span data-stu-id="2732d-107">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="2732d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2732d-108">Remarks</span></span>  
 <span data-ttu-id="2732d-109">Значение недопустимо `assemblyId` для информационного запроса после возврата метода [ICorProfilerCallback:: ассемблюнлоадстартед](icorprofilercallback-assemblyunloadstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2732d-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="2732d-110">Некоторые части выгрузки сборки могут продолжаться после `AssemblyUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2732d-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="2732d-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="2732d-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2732d-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть выгрузки сборки завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="2732d-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2732d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2732d-113">Requirements</span></span>  
 <span data-ttu-id="2732d-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2732d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2732d-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2732d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2732d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2732d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2732d-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2732d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2732d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2732d-118">See also</span></span>

- [<span data-ttu-id="2732d-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2732d-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
