---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495260"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="5ba41-102">Метод ICorProfilerInfo8:: GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="5ba41-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="5ba41-103">Сопоставляет указатель инструкции управляемого кода с FunctionID.</span><span class="sxs-lookup"><span data-stu-id="5ba41-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="5ba41-104">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="5ba41-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ba41-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ba41-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="5ba41-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ba41-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="5ba41-107">\[in] указатель инструкций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="5ba41-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="5ba41-108">\[out] идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="5ba41-108">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="5ba41-109">\[out] удостоверение JIT-повторно скомпилированной версии функции.</span><span class="sxs-lookup"><span data-stu-id="5ba41-109">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ba41-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ba41-110">Remarks</span></span>

<span data-ttu-id="5ba41-111">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="5ba41-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="5ba41-112">Это надмножество [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), который работает только для функций с метаданными.</span><span class="sxs-lookup"><span data-stu-id="5ba41-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ba41-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5ba41-113">Requirements</span></span>

<span data-ttu-id="5ba41-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ba41-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5ba41-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ba41-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5ba41-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ba41-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5ba41-117">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5ba41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5ba41-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5ba41-118">See also</span></span>

- [<span data-ttu-id="5ba41-119">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="5ba41-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
