---
title: Метод ICorProfilerInfo3::GetAppDomainsContainingModule
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
ms.openlocfilehash: 5cc3436716bcfc2ed0f9fd7ff7982bac7a48de9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731206"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="b9f8a-102">Метод ICorProfilerInfo3::GetAppDomainsContainingModule</span><span class="sxs-lookup"><span data-stu-id="b9f8a-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>

<span data-ttu-id="b9f8a-103">Возвращает идентификаторы доменов приложений, в которые был загружен указанный модуль.</span><span class="sxs-lookup"><span data-stu-id="b9f8a-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9f8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9f8a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9f8a-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="b9f8a-106">[in] Идентификатор загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="b9f8a-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="b9f8a-107">[in] Размер массива `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="b9f8a-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="b9f8a-108">[out] Указатель на общее число возвращенных элементов.</span><span class="sxs-lookup"><span data-stu-id="b9f8a-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="b9f8a-109">[out] Массив значений идентификаторов доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="b9f8a-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9f8a-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b9f8a-110">Remarks</span></span>  

 <span data-ttu-id="b9f8a-111">Этот метод использует буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="b9f8a-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f8a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b9f8a-112">Requirements</span></span>  

 <span data-ttu-id="b9f8a-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f8a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f8a-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9f8a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9f8a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9f8a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9f8a-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f8a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f8a-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b9f8a-117">See also</span></span>

- [<span data-ttu-id="b9f8a-118">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="b9f8a-118">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b9f8a-119">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b9f8a-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b9f8a-120">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b9f8a-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b9f8a-121">Профилирование</span><span class="sxs-lookup"><span data-stu-id="b9f8a-121">Profiling</span></span>](index.md)
