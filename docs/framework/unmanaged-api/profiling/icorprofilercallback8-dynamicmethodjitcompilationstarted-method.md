---
title: 'ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионстартед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a4c434c5d458602db8a4d582b239d6e57def6ace
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499003"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="39f8c-102">ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионстартед</span><span class="sxs-lookup"><span data-stu-id="39f8c-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="39f8c-103">[Поддерживается в .NET Framework 4,7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="39f8c-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="39f8c-104">Уведомляет профилировщик каждый раз, когда запускается JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="39f8c-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f8c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39f8c-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39f8c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="39f8c-106">Parameters</span></span>  
<span data-ttu-id="39f8c-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="39f8c-107">[in] `functionId`</span></span>  
<span data-ttu-id="39f8c-108">Идентификатор функции в памяти, для которой запускается JIT-компиляция.</span><span class="sxs-lookup"><span data-stu-id="39f8c-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="39f8c-109">[входные] `fIsSafeToBlock` 
 `true` чтобы указать, что блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. `false`чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="39f8c-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="39f8c-110">[входные] `pILHeader` Указатель на первый байт заголовка IL метода.</span><span class="sxs-lookup"><span data-stu-id="39f8c-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="39f8c-111">[входные] `cbILHeader` Число байтов в заголовке IL.</span><span class="sxs-lookup"><span data-stu-id="39f8c-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="39f8c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="39f8c-112">Remarks</span></span>  

<span data-ttu-id="39f8c-113">Этот обратный вызов активируется всякий раз, когда динамический метод компилируется JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="39f8c-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="39f8c-114">Сюда входят различные суррогаты IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="39f8c-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="39f8c-115">Его цель — предоставить средствам записи профилировщика достаточно информации для распознавания скомпилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="39f8c-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="39f8c-116">`functionId`нельзя использовать значения для разрешения их маркеров метаданных, так как динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="39f8c-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="39f8c-117">`pILHeader`Указатель допустим только во время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="39f8c-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="39f8c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="39f8c-118">Requirements</span></span>  
 <span data-ttu-id="39f8c-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39f8c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f8c-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39f8c-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39f8c-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39f8c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39f8c-122">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39f8c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f8c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="39f8c-123">See also</span></span>

- [<span data-ttu-id="39f8c-124">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="39f8c-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="39f8c-125">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="39f8c-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
