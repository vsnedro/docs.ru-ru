---
title: Метод ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 70d43d7526376c40d0f8358ebd65e4a00a41b969
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701672"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="51c2f-102">Метод ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="51c2f-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>

<span data-ttu-id="51c2f-103">Уведомляет профилировщик о количестве экземпляров каждого указанного класса, созданных с момента последнего сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="51c2f-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51c2f-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="51c2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51c2f-105">Parameters</span></span>  

 `cClassCount`  
 <span data-ttu-id="51c2f-106">окне Размер `classIds` `cObjects` массивов и.</span><span class="sxs-lookup"><span data-stu-id="51c2f-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="51c2f-107">окне Массив идентификаторов классов, где каждый идентификатор указывает класс с одним или несколькими экземплярами.</span><span class="sxs-lookup"><span data-stu-id="51c2f-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="51c2f-108">окне Массив целых чисел, где каждое целое число указывает количество экземпляров для соответствующего класса в `classIds` массиве.</span><span class="sxs-lookup"><span data-stu-id="51c2f-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51c2f-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="51c2f-109">Remarks</span></span>  

 <span data-ttu-id="51c2f-110">`classIds` `cObjects` Массивы и являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="51c2f-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="51c2f-111">Например, `classIds[i]` и `cObjects[i]` сослаться на один и тот же класс.</span><span class="sxs-lookup"><span data-stu-id="51c2f-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="51c2f-112">Если с момента предыдущего сбора мусора экземпляр класса не был создан, класс опускается.</span><span class="sxs-lookup"><span data-stu-id="51c2f-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="51c2f-113">`ObjectsAllocatedByClass`Обратный вызов не будет сообщать объекты, выделенные в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="51c2f-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="51c2f-114">Числа, сообщаемые, `ObjectsAllocatedByClass` являются приблизительными.</span><span class="sxs-lookup"><span data-stu-id="51c2f-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="51c2f-115">Для точного числа счетчиков используйте параметр [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="51c2f-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="51c2f-116">`classIds`Массив может содержать одну или несколько записей null, если соответствующий `cObjects` массив имеет типы, выгрузка которых выполняется.</span><span class="sxs-lookup"><span data-stu-id="51c2f-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51c2f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="51c2f-117">Requirements</span></span>  

 <span data-ttu-id="51c2f-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51c2f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51c2f-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51c2f-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51c2f-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51c2f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51c2f-121">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51c2f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c2f-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="51c2f-122">See also</span></span>

- [<span data-ttu-id="51c2f-123">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="51c2f-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
