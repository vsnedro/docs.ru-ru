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
ms.openlocfilehash: 6354667e754da42692cc0de2dc5330c56f951aa1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725447"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="ffa6c-102">ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионфинишед</span><span class="sxs-lookup"><span data-stu-id="ffa6c-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>

<span data-ttu-id="ffa6c-103">[Поддерживается в .NET Framework 4,7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="ffa6c-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="ffa6c-104">Уведомляет профилировщик о завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa6c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffa6c-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffa6c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffa6c-106">Parameters</span></span>  

<span data-ttu-id="ffa6c-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="ffa6c-107">[in] `functionId`</span></span>  
<span data-ttu-id="ffa6c-108">Идентификатор функции в памяти, для которой запускается JIT-компиляция.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="ffa6c-109">[входные] `hrStatus` Значение, указывающее, была ли JIT-компиляция успешной.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="ffa6c-110">[входные] `fIsSafeToBlock` 
 `true` чтобы указать, что блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. `false`чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="ffa6c-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ffa6c-111">Remarks</span></span>  

<span data-ttu-id="ffa6c-112">Этот обратный вызов активируется каждый раз, когда JIT-компиляция динамического метода завершается.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="ffa6c-113">Сюда входят различные суррогаты IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="ffa6c-114">Его цель — предоставить средствам записи профилировщика достаточно информации для распознавания скомпилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="ffa6c-115">`functionId` нельзя использовать значения для разрешения их маркеров метаданных, так как динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="ffa6c-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="ffa6c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ffa6c-116">Requirements</span></span>  

 <span data-ttu-id="ffa6c-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffa6c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa6c-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ffa6c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ffa6c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffa6c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffa6c-120">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa6c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa6c-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ffa6c-121">See also</span></span>

- [<span data-ttu-id="ffa6c-122">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="ffa6c-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="ffa6c-123">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="ffa6c-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
