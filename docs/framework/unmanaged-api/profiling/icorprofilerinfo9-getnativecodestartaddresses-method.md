---
title: 'ICorProfilerInfo9:: Жетнативекодестартаддрессес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ca1643dfa980fa647164accf6432082428124acb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541243"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="07de4-102">Метод ICorProfilerInfo9:: Жетнативекодестартаддрессес</span><span class="sxs-lookup"><span data-stu-id="07de4-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="07de4-103">При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.</span><span class="sxs-lookup"><span data-stu-id="07de4-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="07de4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07de4-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="07de4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="07de4-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="07de4-106">\[in] идентификатор функции, для которой должны возвращаться начальные адреса машинного кода.</span><span class="sxs-lookup"><span data-stu-id="07de4-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="07de4-107">\[in] Идентификация JIT-повторно скомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="07de4-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="07de4-108">\[in] максимальный размер `codeStartAddresses` массива.</span><span class="sxs-lookup"><span data-stu-id="07de4-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="07de4-109">\[out] количество доступных адресов.</span><span class="sxs-lookup"><span data-stu-id="07de4-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="07de4-110">\[out] массив `UINT_PTR` , каждый из которых является начальным адресом для собственного тела для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="07de4-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="07de4-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="07de4-111">Remarks</span></span>

<span data-ttu-id="07de4-112">Если включена многоуровневая компиляция, функция может иметь более одного тела машинного кода.</span><span class="sxs-lookup"><span data-stu-id="07de4-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="07de4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="07de4-113">Requirements</span></span>

<span data-ttu-id="07de4-114">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="07de4-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="07de4-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07de4-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="07de4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07de4-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="07de4-117">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07de4-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="07de4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="07de4-118">See also</span></span>

- [<span data-ttu-id="07de4-119">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="07de4-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
