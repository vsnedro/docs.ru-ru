---
title: 'ICorProfilerInfo10:: Суспендрунтиме'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 121ed0401628193f6e2fe632a124c08aad7bd1b4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551443"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="485cf-102">Метод ICorProfilerInfo10:: Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="485cf-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="485cf-103">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="485cf-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="485cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="485cf-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="485cf-105">Требования</span><span class="sxs-lookup"><span data-stu-id="485cf-105">Requirements</span></span>

<span data-ttu-id="485cf-106">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="485cf-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="485cf-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="485cf-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="485cf-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="485cf-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="485cf-109">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="485cf-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="485cf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="485cf-110">See also</span></span>

- [<span data-ttu-id="485cf-111">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="485cf-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
