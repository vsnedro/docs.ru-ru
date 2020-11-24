---
title: Метод ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 56468fd38bc110318e04d9b1beda61e279f731d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685324"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="0188f-102">Метод ICorProfilerAssemblyReferenceProvider::AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="0188f-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>

<span data-ttu-id="0188f-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="0188f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0188f-104">Информирует среду CLR о ссылке сборки, которую профилировщик планирует добавить в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0188f-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0188f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0188f-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0188f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0188f-106">Parameters</span></span>

- `pAssemblyRefInfo`

  <span data-ttu-id="0188f-107">Указатель на структуру [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) , которая предоставляет среде CLR сведения о ссылке на сборку, которую следует учитывать при выполнении анализа закрытия ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="0188f-107">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0188f-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0188f-108">Remarks</span></span>  

 <span data-ttu-id="0188f-109">Профилировщик вызывает этот метод для каждой целевой сборки, на которую планируется ссылаться из сборки, указанной в `wszAssemblyPath` аргументе обратного вызова [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0188f-109">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="0188f-110">Объект интерфейса [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) передается обратному вызову [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) профилировщика вместе с путем к сборке и именем в `wszAssemblyPath` аргументе.</span><span class="sxs-lookup"><span data-stu-id="0188f-110">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0188f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0188f-111">Requirements</span></span>  

 <span data-ttu-id="0188f-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0188f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0188f-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0188f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0188f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0188f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0188f-115">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0188f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0188f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0188f-116">See also</span></span>

- [<span data-ttu-id="0188f-117">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="0188f-117">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="0188f-118">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="0188f-118">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="0188f-119">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="0188f-119">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
