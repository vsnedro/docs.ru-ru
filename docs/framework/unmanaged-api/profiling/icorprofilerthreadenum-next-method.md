---
title: Метод ICorProfilerThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
ms.openlocfilehash: dc8e85c5a6047ad5dd99520b57789605333d5bf2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721209"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="c691a-102">Метод ICorProfilerThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c691a-102">ICorProfilerThreadEnum::Next Method</span></span>

<span data-ttu-id="c691a-103">Возвращает заданное число смежных потоков из упорядоченной коллекции потоков начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="c691a-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c691a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c691a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c691a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c691a-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="c691a-106">[in] Количество потоков для извлечения.</span><span class="sxs-lookup"><span data-stu-id="c691a-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="c691a-107">[out] Массив значений `ThreadID`, каждое из которых представляет полученный поток.</span><span class="sxs-lookup"><span data-stu-id="c691a-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c691a-108">[out] Указатель на число потоков, фактически извлеченных в массив `ids`.</span><span class="sxs-lookup"><span data-stu-id="c691a-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c691a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c691a-109">Return Value</span></span>  

 <span data-ttu-id="c691a-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="c691a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c691a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c691a-111">HRESULT</span></span>|<span data-ttu-id="c691a-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="c691a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c691a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c691a-113">S_OK</span></span>|<span data-ttu-id="c691a-114">Возвращенные элементы `celt`.</span><span class="sxs-lookup"><span data-stu-id="c691a-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="c691a-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c691a-115">S_FALSE</span></span>|<span data-ttu-id="c691a-116">Было возвращено элементов менее, чем `celt`, что указывает, что перечисление завершено.</span><span class="sxs-lookup"><span data-stu-id="c691a-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c691a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c691a-117">Requirements</span></span>  

 <span data-ttu-id="c691a-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c691a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c691a-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c691a-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c691a-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c691a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c691a-121">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c691a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c691a-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c691a-122">See also</span></span>

- [<span data-ttu-id="c691a-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="c691a-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="c691a-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="c691a-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
