---
title: Метод ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: b587f30a01623c6e9806bcd9d01058a0880be239
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499913"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="79a5c-102">Метод ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="79a5c-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="79a5c-103">Уведомляет профилировщик о получении сведений о корневых ссылках после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="79a5c-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79a5c-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="79a5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79a5c-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="79a5c-106">окне Число ссылок в `rootRefIds` массиве.</span><span class="sxs-lookup"><span data-stu-id="79a5c-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="79a5c-107">окне Массив идентификаторов объектов, ссылающихся либо на статический объект, либо на объект в стеке.</span><span class="sxs-lookup"><span data-stu-id="79a5c-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a5c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="79a5c-108">Remarks</span></span>  
 <span data-ttu-id="79a5c-109">`RootReferences`Для уведомления профилировщика вызываются методы и [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="79a5c-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="79a5c-110">Профилировщики обычно реализуют один или другой, но не оба, так как передаваемые сведения `RootReferences2` являются надмножеством переданного `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="79a5c-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="79a5c-111">`rootRefIds`Массив может содержать пустой объект.</span><span class="sxs-lookup"><span data-stu-id="79a5c-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="79a5c-112">Например, все ссылки на объекты, объявленные в стеке, рассматриваются сборщиком мусора как корни и всегда будут сообщать о них.</span><span class="sxs-lookup"><span data-stu-id="79a5c-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="79a5c-113">Идентификаторы объектов, возвращаемые, `RootReferences` недопустимы во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старых адресов в новые адреса.</span><span class="sxs-lookup"><span data-stu-id="79a5c-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="79a5c-114">Таким образом, профилировщики не должны пытаться проверять объекты во время `RootReferences` вызова.</span><span class="sxs-lookup"><span data-stu-id="79a5c-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="79a5c-115">При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) все объекты были перемещены в новые расположения и могут быть безопасно проверены.</span><span class="sxs-lookup"><span data-stu-id="79a5c-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a5c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="79a5c-116">Requirements</span></span>  
 <span data-ttu-id="79a5c-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79a5c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a5c-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79a5c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79a5c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79a5c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79a5c-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a5c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a5c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="79a5c-121">See also</span></span>

- [<span data-ttu-id="79a5c-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="79a5c-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
