---
title: 'ICorProfilerInfo10:: Рекуестрежитвисинлинерс'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: e3d5a09730cb8e477bd506749017a403acff1696
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540571"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="f0774-102">Метод ICorProfilerInfo10:: Рекуестрежитвисинлинерс</span><span class="sxs-lookup"><span data-stu-id="f0774-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="f0774-103">Режитс запрошенные методы, а также любые запрашиваются методы.</span><span class="sxs-lookup"><span data-stu-id="f0774-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0774-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0774-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="f0774-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0774-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="f0774-106">\[in] битовая маска [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f0774-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="f0774-107">\[в] число функций для повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="f0774-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="f0774-108">\[в] задает `moduleId` часть `module` пар (, `methodDef` ), определяющих функции для повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="f0774-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="f0774-109">\[в] задает `methodId` часть `module` пар (, `methodDef` ), определяющих функции для повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="f0774-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0774-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0774-110">Remarks</span></span>

<span data-ttu-id="f0774-111">[Рекуестрежит](icorprofilerinfo4-requestrejit-method.md) не выполняет отслеживание встроенных методов.</span><span class="sxs-lookup"><span data-stu-id="f0774-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="f0774-112">Профилировщик ожидал блокировать встраивание или отслеживание встраивания, а также вызов `RequestReJIT` всех строк, чтобы гарантировать, что каждый экземпляр встроенного метода был режиттед.</span><span class="sxs-lookup"><span data-stu-id="f0774-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="f0774-113">Это создает проблему с ReJIT при присоединении, так как профилировщик отсутствует для мониторинга встраивания.</span><span class="sxs-lookup"><span data-stu-id="f0774-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="f0774-114">Этот метод может быть вызван, чтобы гарантировать, что полный набор Режиттед также будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="f0774-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0774-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f0774-115">Requirements</span></span>

<span data-ttu-id="f0774-116">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="f0774-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="f0774-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0774-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f0774-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0774-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f0774-119">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0774-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f0774-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f0774-120">See also</span></span>

- [<span data-ttu-id="f0774-121">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="f0774-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
