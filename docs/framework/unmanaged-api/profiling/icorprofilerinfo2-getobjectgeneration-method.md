---
title: Метод ICorProfilerInfo2::GetObjectGeneration
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
ms.openlocfilehash: 4ba404692bef84c0522a799c61f07eac341eaab4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703854"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="e0f35-102">Метод ICorProfilerInfo2::GetObjectGeneration</span><span class="sxs-lookup"><span data-stu-id="e0f35-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>

<span data-ttu-id="e0f35-103">Возвращает сегмент кучи, который содержит указанный объект.</span><span class="sxs-lookup"><span data-stu-id="e0f35-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0f35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0f35-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0f35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0f35-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="e0f35-106">окне Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="e0f35-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="e0f35-107">заполняет Указатель на структуру [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , описывающую диапазон (т. е. блок) памяти в поколении, которое является сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="e0f35-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="e0f35-108">Этот диапазон содержит указанный объект.</span><span class="sxs-lookup"><span data-stu-id="e0f35-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0f35-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e0f35-109">Remarks</span></span>  

 <span data-ttu-id="e0f35-110">`GetObjectGeneration`Метод может быть вызван из любого обратного вызова профилировщика при условии, что сборка мусора не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e0f35-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="e0f35-111">То есть он может быть вызван из любого обратного вызова, за исключением тех, которые происходят между [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) и [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0f35-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0f35-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e0f35-112">Requirements</span></span>  

 <span data-ttu-id="e0f35-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f35-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0f35-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0f35-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0f35-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0f35-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0f35-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0f35-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f35-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0f35-117">See also</span></span>

- [<span data-ttu-id="e0f35-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e0f35-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e0f35-119">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="e0f35-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
