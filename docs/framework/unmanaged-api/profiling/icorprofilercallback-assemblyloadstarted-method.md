---
title: Метод ICorProfilerCallback::AssemblyLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: df172edb97a82ae3bf2d46c8be6ea05d5445a09a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500433"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="92c85-102">Метод ICorProfilerCallback::AssemblyLoadStarted</span><span class="sxs-lookup"><span data-stu-id="92c85-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="92c85-103">Уведомляет профилировщик о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="92c85-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92c85-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92c85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92c85-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="92c85-106">\[в] определяет загружаемую сборку.</span><span class="sxs-lookup"><span data-stu-id="92c85-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="92c85-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="92c85-107">Remarks</span></span>  
 <span data-ttu-id="92c85-108">Значение недопустимо `assemblyId` для информационного запроса, пока не будет вызван метод [ICorProfilerCallback:: AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="92c85-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c85-109">Требования</span><span class="sxs-lookup"><span data-stu-id="92c85-109">Requirements</span></span>  
 <span data-ttu-id="92c85-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92c85-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c85-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92c85-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92c85-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92c85-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92c85-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92c85-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c85-114">См. также</span><span class="sxs-lookup"><span data-stu-id="92c85-114">See also</span></span>

- [<span data-ttu-id="92c85-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="92c85-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
