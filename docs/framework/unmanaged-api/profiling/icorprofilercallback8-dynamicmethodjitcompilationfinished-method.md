---
title: 'ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионфинишед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 554cc93de934061e87322c7557e05545e5e7bc62
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499081"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="3d6c8-102">ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионфинишед</span><span class="sxs-lookup"><span data-stu-id="3d6c8-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="3d6c8-103">[Поддерживается в .NET Framework 4,7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="3d6c8-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="3d6c8-104">Уведомляет профилировщик о завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6c8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d6c8-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d6c8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d6c8-106">Parameters</span></span>  
<span data-ttu-id="3d6c8-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="3d6c8-107">[in] `functionId`</span></span>  
<span data-ttu-id="3d6c8-108">Идентификатор функции в памяти, для которой запускается JIT-компиляция.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="3d6c8-109">[входные] `hrStatus` Значение, указывающее, была ли JIT-компиляция успешной.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="3d6c8-110">[входные] `fIsSafeToBlock` 
 `true` чтобы указать, что блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. `false`чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="3d6c8-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d6c8-111">Remarks</span></span>  

<span data-ttu-id="3d6c8-112">Этот обратный вызов активируется каждый раз, когда JIT-компиляция динамического метода завершается.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="3d6c8-113">Сюда входят различные суррогаты IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="3d6c8-114">Его цель — предоставить средствам записи профилировщика достаточно информации для распознавания скомпилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="3d6c8-115">`functionId`нельзя использовать значения для разрешения их маркеров метаданных, так как динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="3d6c8-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d6c8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3d6c8-116">Requirements</span></span>  
 <span data-ttu-id="3d6c8-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d6c8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d6c8-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d6c8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d6c8-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d6c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d6c8-120">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d6c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6c8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3d6c8-121">See also</span></span>

- [<span data-ttu-id="3d6c8-122">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="3d6c8-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="3d6c8-123">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="3d6c8-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
