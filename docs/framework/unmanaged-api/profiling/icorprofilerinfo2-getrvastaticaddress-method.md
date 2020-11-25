---
title: Метод ICorProfilerInfo2::GetRVAStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
ms.openlocfilehash: ea4f6f129cf2919124b1bef1fd837f2b1e13760e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727059"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="94fad-102">Метод ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="94fad-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>

<span data-ttu-id="94fad-103">Возвращает адрес указанного статического поля с относительным виртуальным адресом (RVA).</span><span class="sxs-lookup"><span data-stu-id="94fad-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94fad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94fad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94fad-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="94fad-106">окне Идентификатор класса, содержащего запрошенное статическое поле для параметра RVA.</span><span class="sxs-lookup"><span data-stu-id="94fad-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="94fad-107">окне Токен метаданных для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="94fad-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="94fad-108">заполняет Указатель на адрес поля static-RVA.</span><span class="sxs-lookup"><span data-stu-id="94fad-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94fad-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="94fad-109">Remarks</span></span>  

 <span data-ttu-id="94fad-110">`GetRVAStaticAddress`Метод может вернуть одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="94fad-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="94fad-111">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="94fad-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="94fad-112">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="94fad-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="94fad-113">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="94fad-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="94fad-114">Перед завершением конструктора класса класса возвратит `GetRVAStaticAddress` CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и могут быть корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="94fad-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fad-115">Требования</span><span class="sxs-lookup"><span data-stu-id="94fad-115">Requirements</span></span>  

 <span data-ttu-id="94fad-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94fad-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fad-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94fad-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94fad-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94fad-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94fad-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fad-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fad-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94fad-120">See also</span></span>

- [<span data-ttu-id="94fad-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="94fad-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="94fad-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="94fad-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
