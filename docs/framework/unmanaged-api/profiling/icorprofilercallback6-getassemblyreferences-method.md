---
title: Метод ICorProfilerCallback6::GetAssemblyReferences
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
ms.openlocfilehash: c9e973009f46ef7e554ee2df63493464f4956342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725486"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="4e700-102">Метод ICorProfilerCallback6::GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="4e700-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>

<span data-ttu-id="4e700-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="4e700-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4e700-104">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="4e700-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e700-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e700-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e700-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e700-106">Parameters</span></span>  

 `wszAssemblyPath`  
 <span data-ttu-id="4e700-107">[в] Путь и имя сборки, метаданные которой будут изменены.</span><span class="sxs-lookup"><span data-stu-id="4e700-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="4e700-108">окне Указатель на адрес интерфейса [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) , указывающий ссылки на сборку для добавления.</span><span class="sxs-lookup"><span data-stu-id="4e700-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e700-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4e700-109">Return Value</span></span>  

 <span data-ttu-id="4e700-110">Значения, возвращаемые из этого обратного вызова, игнорируются.</span><span class="sxs-lookup"><span data-stu-id="4e700-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e700-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4e700-111">Remarks</span></span>  

 <span data-ttu-id="4e700-112">Этот обратный вызов управляется путем установки флага [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) маски событий при вызове метода [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4e700-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="4e700-113">Если профилировщик регистрируется для метода обратного вызова [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , среда выполнения передает путь и имя загружаемой сборки вместе с указателем на объект интерфейса [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) для этого метода.</span><span class="sxs-lookup"><span data-stu-id="4e700-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="4e700-114">Затем профилировщик может вызвать метод [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) с `COR_PRF_ASSEMBLY_REFERENCE_INFO` объектом для каждой целевой сборки, на которую планируется ссылаться из сборки, указанной в `GetAssemblyReferences` обратном вызове.</span><span class="sxs-lookup"><span data-stu-id="4e700-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="4e700-115">Используйте обратный вызов `GetAssemblyReferences`, только если для добавления ссылок на сборку профилировщик должен изменить метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="4e700-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="4e700-116">(Но обратите внимание, что фактическое изменение метаданных сборки выполняется в методе обратного вызова [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).) Профилировщик должен реализовать `GetAssemblyReferences` метод обратного вызова, чтобы сообщить среде CLR о том, что ссылки на сборки будут добавлены при загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="4e700-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="4e700-117">Это гарантирует, что решения о предоставлении общего доступа к сборке, сделанные средой CLR во время этой ранней стадии, остаются в силе, хотя позже профилировщик планирует изменить ссылки на сборку метаданных.</span><span class="sxs-lookup"><span data-stu-id="4e700-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="4e700-118">Это поможет избежать некоторых случаев, при которых модификации метаданных профилировщика приводят к ошибке `SECURITY_E_INCOMPATIBLE_SHARE`.</span><span class="sxs-lookup"><span data-stu-id="4e700-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="4e700-119">Профилировщик использует объект [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) , предоставленный этим методом, для добавления ссылок на сборки в обход закрытия ссылок на сборки CLR.</span><span class="sxs-lookup"><span data-stu-id="4e700-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="4e700-120">Объект [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) должен использоваться только в этом обратном вызове.</span><span class="sxs-lookup"><span data-stu-id="4e700-120">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="4e700-121">Вызовы метода [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) из этого обратного вызова не приводят к изменению метаданных, но только в измененном анализе закрытия ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="4e700-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="4e700-122">Профилировщику по-прежнему придется использовать объект [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) , чтобы явно добавлять ссылки на сборки из обратного вызова [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) для ссылающейся сборки, даже если она реализует `GetAssemblyReferences` обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="4e700-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="4e700-123">Профилировщик должен быть готов к получению повторяющихся вызовов этого обратного вызова для одной и той же сборки и должен одинаково реагировать на каждый такой повторный вызов (путем выполнения одного и того же набора вызовов [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="4e700-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e700-124">Требования</span><span class="sxs-lookup"><span data-stu-id="4e700-124">Requirements</span></span>  

 <span data-ttu-id="4e700-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e700-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e700-126">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e700-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e700-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e700-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e700-128">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e700-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e700-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e700-129">See also</span></span>

- [<span data-ttu-id="4e700-130">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="4e700-130">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="4e700-131">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="4e700-131">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="4e700-132">Структура COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="4e700-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="4e700-133">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="4e700-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
