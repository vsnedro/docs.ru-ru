---
title: Метод ICorProfilerThreadEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: 12b7b53c408388c21d7508f6591ead5ccf55936b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721183"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="72b94-102">Метод ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="72b94-102">ICorProfilerThreadEnum::Skip Method</span></span>

<span data-ttu-id="72b94-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="72b94-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72b94-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72b94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72b94-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="72b94-106">окне Число пропущенных элементов.</span><span class="sxs-lookup"><span data-stu-id="72b94-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72b94-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="72b94-107">Return Value</span></span>  

 <span data-ttu-id="72b94-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="72b94-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="72b94-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72b94-109">HRESULT</span></span>|<span data-ttu-id="72b94-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="72b94-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72b94-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="72b94-111">S_OK</span></span>|<span data-ttu-id="72b94-112">`celt` элементы пропущены.</span><span class="sxs-lookup"><span data-stu-id="72b94-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="72b94-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="72b94-113">S_FALSE</span></span>|<span data-ttu-id="72b94-114">`celt`Пропущено меньше элементов, что означает, что больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="72b94-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72b94-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="72b94-115">Remarks</span></span>  

 <span data-ttu-id="72b94-116">Новая позиции курсора перечислителя — (Текущая позиции) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="72b94-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b94-117">Требования</span><span class="sxs-lookup"><span data-stu-id="72b94-117">Requirements</span></span>  

 <span data-ttu-id="72b94-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72b94-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b94-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72b94-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72b94-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72b94-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72b94-121">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b94-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b94-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="72b94-122">See also</span></span>

- [<span data-ttu-id="72b94-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="72b94-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="72b94-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="72b94-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
