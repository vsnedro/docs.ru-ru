---
title: Метод ICorProfilerCallback::ObjectReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 9485e3ca657ab108d2bcc9d00b1c475f8ee3c086
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703958"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="d5b69-102">Метод ICorProfilerCallback::ObjectReferences</span><span class="sxs-lookup"><span data-stu-id="d5b69-102">ICorProfilerCallback::ObjectReferences Method</span></span>

<span data-ttu-id="d5b69-103">Уведомляет профилировщик об объектах в памяти, на которые ссылается указанный объект.</span><span class="sxs-lookup"><span data-stu-id="d5b69-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5b69-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5b69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5b69-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="d5b69-106">окне Идентификатор объекта, ссылающегося на объекты.</span><span class="sxs-lookup"><span data-stu-id="d5b69-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="d5b69-107">окне Идентификатор класса, экземпляр которого является указанным объектом.</span><span class="sxs-lookup"><span data-stu-id="d5b69-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="d5b69-108">окне Количество объектов, на которые ссылается указанный объект (то есть количество элементов в `objectRefIds` массиве).</span><span class="sxs-lookup"><span data-stu-id="d5b69-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="d5b69-109">окне Массив идентификаторов объектов, на которые ссылается `objectId` .</span><span class="sxs-lookup"><span data-stu-id="d5b69-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5b69-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d5b69-110">Remarks</span></span>  

 <span data-ttu-id="d5b69-111">`ObjectReferences`Метод вызывается для каждого объекта, остающегося в куче после завершения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d5b69-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="d5b69-112">Если профилировщик возвращает ошибку из этого обратного вызова, службы профилирования будут прекращены вызовом этого обратного вызова до следующей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d5b69-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="d5b69-113">`ObjectReferences`Обратный вызов можно использовать в сочетании с обратным вызовом [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) , чтобы создать полный граф ссылки на объект для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5b69-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="d5b69-114">Общеязыковая среда выполнения (CLR) гарантирует, что в методе каждый раз сообщается ссылка на каждый объект `ObjectReferences` .</span><span class="sxs-lookup"><span data-stu-id="d5b69-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="d5b69-115">Идентификаторы объектов, возвращаемые, `ObjectReferences` недопустимы во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов.</span><span class="sxs-lookup"><span data-stu-id="d5b69-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="d5b69-116">Таким образом, профилировщики не должны пытаться проверять объекты во время `ObjectReferences` вызова.</span><span class="sxs-lookup"><span data-stu-id="d5b69-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="d5b69-117">При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) сборка мусора завершается, и проверка может быть безопасно выполнена.</span><span class="sxs-lookup"><span data-stu-id="d5b69-117">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="d5b69-118">Значение NULL `ClassId` указывает, что `objectId` имеет тип, который выгружается.</span><span class="sxs-lookup"><span data-stu-id="d5b69-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b69-119">Требования</span><span class="sxs-lookup"><span data-stu-id="d5b69-119">Requirements</span></span>  

 <span data-ttu-id="d5b69-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5b69-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b69-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5b69-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5b69-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5b69-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5b69-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b69-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b69-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5b69-124">See also</span></span>

- [<span data-ttu-id="d5b69-125">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d5b69-125">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
