---
title: Интерфейс ICorProfilerAssemblyReferenceProvider
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 2cee012be2665f5a7212600ec11e401b18160d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691400"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="970cf-102">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="970cf-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>

<span data-ttu-id="970cf-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="970cf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="970cf-104">Позволяет профилировщику информировать среду CLR о ссылках на сборки, которые профилировщик добавит в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="970cf-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="970cf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="970cf-105">Methods</span></span>  
  
|<span data-ttu-id="970cf-106">Метод</span><span class="sxs-lookup"><span data-stu-id="970cf-106">Method</span></span>|<span data-ttu-id="970cf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="970cf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="970cf-108">Метод AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="970cf-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="970cf-109">Сообщает CLR о сборке, которую профилировщик планирует добавить в обратный вызов [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="970cf-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="970cf-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="970cf-110">Remarks</span></span>  

 <span data-ttu-id="970cf-111">Среда CLR передает профилировщику `ICorProfilerAssemblyReferenceProvider` объект интерфейса в обратном вызове [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="970cf-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="970cf-112">Это позволяет профилировщику информировать среду CLR о ссылках на сборки, которые профилировщик планирует добавить позднее в параметре [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="970cf-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="970cf-113">callback.</span><span class="sxs-lookup"><span data-stu-id="970cf-113">callback.</span></span> <span data-ttu-id="970cf-114">В результате повышается точность обхода замыкания ссылки на сборку среды CLR и его алгоритмов, определяющих возможность совместного доступа к сборкам.</span><span class="sxs-lookup"><span data-stu-id="970cf-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="970cf-115">Этот интерфейс можно использовать только в обратном вызове [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , который передает этот объект интерфейса профилировщику.</span><span class="sxs-lookup"><span data-stu-id="970cf-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="970cf-116">Требования</span><span class="sxs-lookup"><span data-stu-id="970cf-116">Requirements</span></span>  

 <span data-ttu-id="970cf-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="970cf-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="970cf-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="970cf-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="970cf-119">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="970cf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970cf-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="970cf-120">See also</span></span>

- [<span data-ttu-id="970cf-121">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="970cf-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
