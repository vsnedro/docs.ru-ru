---
title: 'ICorProfilerInfo10:: Жетлохобжектсизесрешолд'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 280f0a401f87f81e1ef9d4a2c85c06599442b5ec
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543950"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="875d1-102">Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="875d1-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="875d1-103">Возвращает значение заданного порога кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="875d1-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="875d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="875d1-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="875d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="875d1-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="875d1-106">\[out] пороговое значение кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="875d1-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="875d1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="875d1-107">Remarks</span></span>

<span data-ttu-id="875d1-108">Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="875d1-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="875d1-109">Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, он `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="875d1-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="875d1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="875d1-110">Requirements</span></span>

<span data-ttu-id="875d1-111">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="875d1-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="875d1-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="875d1-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="875d1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="875d1-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="875d1-114">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="875d1-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="875d1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="875d1-115">See also</span></span>

- [<span data-ttu-id="875d1-116">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="875d1-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
