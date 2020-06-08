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
ms.openlocfilehash: 80054a8292c69b957664cb3573b0a8694c7f9fd2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500407"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="45680-102">Метод ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="45680-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="45680-103">Уведомляет профилировщик о выгрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="45680-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45680-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45680-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45680-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="45680-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="45680-106">\[в] определяет сборку, которая выгружается.</span><span class="sxs-lookup"><span data-stu-id="45680-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="45680-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="45680-107">Remarks</span></span>  
 <span data-ttu-id="45680-108">Значение недопустимо `assemblyId` для информационного запроса после `AssemblyUnloadStarted` возврата метода — это последний шанс профилировщика получить сведения об этой сборке.</span><span class="sxs-lookup"><span data-stu-id="45680-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45680-109">Требования</span><span class="sxs-lookup"><span data-stu-id="45680-109">Requirements</span></span>  
 <span data-ttu-id="45680-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45680-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45680-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45680-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45680-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45680-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45680-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45680-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45680-114">См. также</span><span class="sxs-lookup"><span data-stu-id="45680-114">See also</span></span>

- [<span data-ttu-id="45680-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="45680-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="45680-116">Метод AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="45680-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
