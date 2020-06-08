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
ms.openlocfilehash: 525fa2efa39909390d874fb97d9f11e647340ea9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496949"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="2685b-102">Метод ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="2685b-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="2685b-103">Возвращает адрес указанного статического поля с относительным виртуальным адресом (RVA).</span><span class="sxs-lookup"><span data-stu-id="2685b-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2685b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2685b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2685b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2685b-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2685b-106">окне Идентификатор класса, содержащего запрошенное статическое поле для параметра RVA.</span><span class="sxs-lookup"><span data-stu-id="2685b-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="2685b-107">окне Токен метаданных для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="2685b-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="2685b-108">заполняет Указатель на адрес поля static-RVA.</span><span class="sxs-lookup"><span data-stu-id="2685b-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2685b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2685b-109">Remarks</span></span>  
 <span data-ttu-id="2685b-110">`GetRVAStaticAddress`Метод может вернуть одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="2685b-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="2685b-111">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="2685b-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="2685b-112">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2685b-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="2685b-113">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="2685b-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="2685b-114">Перед завершением конструктора класса класса возвратит `GetRVAStaticAddress` CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и могут быть корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2685b-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2685b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2685b-115">Requirements</span></span>  
 <span data-ttu-id="2685b-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2685b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2685b-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2685b-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2685b-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2685b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2685b-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2685b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2685b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2685b-120">See also</span></span>

- [<span data-ttu-id="2685b-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2685b-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2685b-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="2685b-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
