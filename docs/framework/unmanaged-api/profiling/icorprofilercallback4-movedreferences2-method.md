---
title: Метод ICorProfilerCallback4::MovedReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 41f7010b6c13327e45a4da7fdae1b9e1fe6e41a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730283"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="22edd-102">Метод ICorProfilerCallback4::MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="22edd-102">ICorProfilerCallback4::MovedReferences2 Method</span></span>

<span data-ttu-id="22edd-103">Вызывается для предоставления сведений о структуре объектов в куче в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="22edd-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="22edd-104">Этот метод вызывается, если профилировщик реализовал интерфейс [ICorProfilerCallback4](icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="22edd-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="22edd-105">Этот обратный вызов заменяет метод [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , поскольку он может сообщать о больших диапазонах объектов, длина которых превышает то, что может быть выражено в ulong.</span><span class="sxs-lookup"><span data-stu-id="22edd-105">This callback replaces the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22edd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22edd-106">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="22edd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="22edd-107">Parameters</span></span>  

 `cMovedObjectIDRanges`  
 <span data-ttu-id="22edd-108">[in] Количество блоков смежных объектов, перемещенных в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="22edd-108">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="22edd-109">Таким образом значение `cMovedObjectIDRanges` представляет общий размер массивов `oldObjectIDRangeStart`, `newObjectIDRangeStart` и `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="22edd-109">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="22edd-110">Следующие три аргумента `MovedReferences2` являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="22edd-110">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="22edd-111">Другими словами, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` и `cObjectIDRangeLength[i]` относятся к одному и тому же блоку смежных объектов.</span><span class="sxs-lookup"><span data-stu-id="22edd-111">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="22edd-112">[in] Массив значений `ObjectID`, каждое из которых является старым (до сборки мусора) начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="22edd-112">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="22edd-113">[in] Массив значений `ObjectID`, каждое из которых является новым (после сборки мусора) начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="22edd-113">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="22edd-114">[in] Массив целых чисел, каждое из которых представляет размер блока смежных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="22edd-114">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="22edd-115">Размер указывается для каждого блока, ссылка на который имеется в массивах `oldObjectIDRangeStart` и `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="22edd-115">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22edd-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="22edd-116">Remarks</span></span>  

 <span data-ttu-id="22edd-117">Сжатие сборки мусора без сжатия освобождает память, занятую "мертвыми" объектами, и сжимает это освобожденное пространство.</span><span class="sxs-lookup"><span data-stu-id="22edd-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="22edd-118">В результате динамические объекты могут быть перемещены в кучу, и значения `ObjectID`, распространенные предыдущими уведомлениями, могут измениться.</span><span class="sxs-lookup"><span data-stu-id="22edd-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="22edd-119">Предположим, что существующее значение `ObjectID` (`oldObjectID`) находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="22edd-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="22edd-120">В этом случае смещение от начала диапазона к началу объекта следующее:</span><span class="sxs-lookup"><span data-stu-id="22edd-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="22edd-121">Для любого значения параметра `i`, который находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="22edd-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="22edd-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="22edd-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="22edd-123">можно вычислить новый `ObjectID` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="22edd-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="22edd-124">`newObjectID` = `newObjectIDRangeStart[i]` + ( `oldObjectID` – `oldObjectIDRangeStart[i]` )</span><span class="sxs-lookup"><span data-stu-id="22edd-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="22edd-125">Ни одно из значений `ObjectID`, переданных `MovedReferences2`, не является допустимым во время самого обратного вызова, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="22edd-125">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="22edd-126">В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `MovedReferences2`.</span><span class="sxs-lookup"><span data-stu-id="22edd-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="22edd-127">Обратный вызов [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) указывает, что все объекты были перемещены в новые расположения, и проверку можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="22edd-127">A [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="22edd-128">Если профилировщик реализует интерфейсы [ICorProfilerCallback](icorprofilercallback-interface.md) и [ICorProfilerCallback4](icorprofilercallback4-interface.md) , `MovedReferences2` метод вызывается перед методом [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , но только в случае `MovedReferences2` успешного возврата методом.</span><span class="sxs-lookup"><span data-stu-id="22edd-128">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="22edd-129">Профилировщики могут возвращать значение HRESULT, указывающее на сбой в методе `MovedReferences2`, что позволяет избежать вызова второго метода.</span><span class="sxs-lookup"><span data-stu-id="22edd-129">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22edd-130">Требования</span><span class="sxs-lookup"><span data-stu-id="22edd-130">Requirements</span></span>  

 <span data-ttu-id="22edd-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22edd-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22edd-132">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22edd-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22edd-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22edd-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22edd-134">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22edd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22edd-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="22edd-135">See also</span></span>

- [<span data-ttu-id="22edd-136">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="22edd-136">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="22edd-137">Метод MovedReferences</span><span class="sxs-lookup"><span data-stu-id="22edd-137">MovedReferences Method</span></span>](icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="22edd-138">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="22edd-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="22edd-139">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="22edd-139">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="22edd-140">Профилирование</span><span class="sxs-lookup"><span data-stu-id="22edd-140">Profiling</span></span>](index.md)
