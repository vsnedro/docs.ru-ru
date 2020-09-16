---
title: 'ICorProfilerInfo10:: Исфрозенобжект'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3755260b885768de6b5b2d6342c0ad590a95caff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548674"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="e951a-102">Метод ICorProfilerInfo10:: Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="e951a-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="e951a-103">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e951a-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="e951a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e951a-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="e951a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e951a-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="e951a-106">\[в] объект для проверки.</span><span class="sxs-lookup"><span data-stu-id="e951a-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="e951a-107">\[out] значение `BOOL` , указывающее, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e951a-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="e951a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e951a-108">Requirements</span></span>

<span data-ttu-id="e951a-109">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="e951a-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="e951a-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e951a-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e951a-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e951a-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e951a-112">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e951a-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e951a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e951a-113">See also</span></span>

- [<span data-ttu-id="e951a-114">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="e951a-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
