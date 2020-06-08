---
title: Метод ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: 527e48d02d5267d6ae41214686c2e8c997d85dca
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499549"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="f85f9-102">Метод ICorProfilerCallback4::GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="f85f9-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="f85f9-103">Позволяет профилировщику кода устанавливать альтернативные флаги создания кода для нового текста перекомпилированного метода.</span><span class="sxs-lookup"><span data-stu-id="f85f9-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f85f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f85f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f85f9-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f85f9-106">окне Модуль, содержащий метод, для которого среда CLR требует параметры JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="f85f9-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="f85f9-107">окне `MethodDef`Метод, для которого среда CLR требует параметры JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="f85f9-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="f85f9-108">окне Указатель на интерфейс [икорпрофилерфунктионконтрол](icorprofilerfunctioncontrol-interface.md) , который профилировщик может использовать для предоставления сведений о JIT-компиляции для метода, для которого выполняется повторная компиляция.</span><span class="sxs-lookup"><span data-stu-id="f85f9-108">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f85f9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f85f9-109">Remarks</span></span>  
 <span data-ttu-id="f85f9-110">Среда CLR выдает `GetReJITParameters` обратный вызов, чтобы профилировщик мог указать параметры для перекомпиляции данного метода.</span><span class="sxs-lookup"><span data-stu-id="f85f9-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="f85f9-111">`GetReJITParameters`Обратный вызов выдается только один раз для каждой функции; параметры, предоставляемые профилировщиком, применяются ко всем экземплярам этой функции.</span><span class="sxs-lookup"><span data-stu-id="f85f9-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f85f9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f85f9-112">Requirements</span></span>  
 <span data-ttu-id="f85f9-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f85f9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85f9-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f85f9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f85f9-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f85f9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f85f9-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f85f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85f9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f85f9-117">See also</span></span>

- [<span data-ttu-id="f85f9-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f85f9-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f85f9-119">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="f85f9-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="f85f9-120">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f85f9-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="f85f9-121">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f85f9-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
