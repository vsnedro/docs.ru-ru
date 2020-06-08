---
title: Метод ICorProfilerInfo2::GetThreadStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
ms.openlocfilehash: 3df6e4decf1c4641116dee5fab3ca83189b427c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496767"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="2c1f7-102">Метод ICorProfilerInfo2::GetThreadStaticAddress</span><span class="sxs-lookup"><span data-stu-id="2c1f7-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="2c1f7-103">Возвращает адрес указанного статического поля потока, который находится в области заданного потока.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c1f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c1f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c1f7-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2c1f7-106">окне Идентификатор класса, содержащего запрошенное статическое поле потока.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="2c1f7-107">окне Токен метаданных для запрошенного статического поля потока.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="2c1f7-108">окне Идентификатор потока, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="2c1f7-109">заполняет Указатель на адрес статического поля, находящихся в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c1f7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c1f7-110">Remarks</span></span>  
 <span data-ttu-id="2c1f7-111">`GetThreadStaticAddress`Метод может вернуть одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="2c1f7-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="2c1f7-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="2c1f7-113">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="2c1f7-114">Эти адреса могут стать недействительными после сборки мусора, поэтому после завершения профилирования сборщиком мусора не следует считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="2c1f7-115">Перед завершением конструктора класса класса возвратит `GetThreadStaticAddress` CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2c1f7-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1f7-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2c1f7-116">Requirements</span></span>  
 <span data-ttu-id="2c1f7-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1f7-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c1f7-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c1f7-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c1f7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c1f7-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1f7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1f7-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2c1f7-121">See also</span></span>

- [<span data-ttu-id="2c1f7-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2c1f7-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2c1f7-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="2c1f7-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
