---
title: Интерфейс ICorProfilerFunctionControl
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 177127c8c53e4fee31f7007d04c49cc337cca458
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498730"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="7cea1-102">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="7cea1-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="7cea1-103">Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="7cea1-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7cea1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7cea1-104">Methods</span></span>  
  
|<span data-ttu-id="7cea1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7cea1-105">Method</span></span>|<span data-ttu-id="7cea1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7cea1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7cea1-107">Метод SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="7cea1-107">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="7cea1-108">Задает один или несколько флагов из перечисления [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) для управления созданием кода для перекомпилированной функции JIT.</span><span class="sxs-lookup"><span data-stu-id="7cea1-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="7cea1-109">Метод SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="7cea1-109">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="7cea1-110">Заменяет тело метода на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="7cea1-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="7cea1-111">Метод SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="7cea1-111">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="7cea1-112">Устанавливает карту кода для указанной функции с помощью указанных записей карты языка CIL.</span><span class="sxs-lookup"><span data-stu-id="7cea1-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cea1-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="7cea1-113">Remarks</span></span>  
 <span data-ttu-id="7cea1-114">Интерфейс `ICorProfilerFunctionControl` предоставляет методы для генерации управляющего кода для одной перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="7cea1-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="7cea1-115">Профилировщик получает экземпляр этого интерфейса через обратный вызов [ICorProfilerCallback4:: жетрежитпараметерс](icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7cea1-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="7cea1-116">Каждый экземпляр `ICorProfilerFunctionControl` управляет всеми экземплярами одной функции.</span><span class="sxs-lookup"><span data-stu-id="7cea1-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cea1-117">Требования</span><span class="sxs-lookup"><span data-stu-id="7cea1-117">Requirements</span></span>  
 <span data-ttu-id="7cea1-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cea1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cea1-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7cea1-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7cea1-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cea1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cea1-121">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cea1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cea1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7cea1-122">See also</span></span>

- [<span data-ttu-id="7cea1-123">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="7cea1-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="7cea1-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="7cea1-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7cea1-125">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="7cea1-125">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
