---
title: Метод ICorProfilerInfo4::EnumThreads
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: df0e66c8563404d7de4f1e11f41483f2f61f519c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721560"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="ef4d5-102">Метод ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="ef4d5-102">ICorProfilerInfo4::EnumThreads Method</span></span>

<span data-ttu-id="ef4d5-103">Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="ef4d5-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef4d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef4d5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef4d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef4d5-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="ef4d5-106">заполняет Указатель на интерфейс [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ef4d5-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef4d5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef4d5-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef4d5-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ef4d5-108">Requirements</span></span>  

 <span data-ttu-id="ef4d5-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef4d5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef4d5-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef4d5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef4d5-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef4d5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef4d5-112">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef4d5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4d5-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ef4d5-113">See also</span></span>

- [<span data-ttu-id="ef4d5-114">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="ef4d5-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="ef4d5-115">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="ef4d5-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="ef4d5-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ef4d5-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ef4d5-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="ef4d5-117">Profiling</span></span>](index.md)
