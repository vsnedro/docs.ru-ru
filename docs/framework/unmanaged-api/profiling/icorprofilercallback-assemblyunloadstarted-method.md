---
title: Метод ICorProfilerCallback::AssemblyUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: bb7dade1ccd46cb9e13d45468c2ca2a8b451b70b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700305"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="1ee38-102">Метод ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="1ee38-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>

<span data-ttu-id="1ee38-103">Уведомляет профилировщик о выгрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="1ee38-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ee38-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ee38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ee38-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="1ee38-106">\[в] определяет сборку, которая выгружается.</span><span class="sxs-lookup"><span data-stu-id="1ee38-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ee38-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1ee38-107">Remarks</span></span>  

 <span data-ttu-id="1ee38-108">Значение недопустимо `assemblyId` для информационного запроса после `AssemblyUnloadStarted` возврата метода — это последний шанс профилировщика получить сведения об этой сборке.</span><span class="sxs-lookup"><span data-stu-id="1ee38-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee38-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1ee38-109">Requirements</span></span>  

 <span data-ttu-id="1ee38-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ee38-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee38-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ee38-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ee38-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ee38-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ee38-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee38-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee38-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ee38-114">See also</span></span>

- [<span data-ttu-id="1ee38-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1ee38-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1ee38-116">Метод AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="1ee38-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
