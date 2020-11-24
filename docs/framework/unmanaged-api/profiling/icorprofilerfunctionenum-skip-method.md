---
title: Метод ICorProfilerFunctionEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: da578e02db0744b1f64c1d392844aa020721e784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669265"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="6b57e-102">Метод ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="6b57e-102">ICorProfilerFunctionEnum::Skip Method</span></span>

<span data-ttu-id="6b57e-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="6b57e-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b57e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b57e-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b57e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b57e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="6b57e-106">окне Число пропущенных элементов.</span><span class="sxs-lookup"><span data-stu-id="6b57e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b57e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6b57e-107">Return Value</span></span>  

 <span data-ttu-id="6b57e-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="6b57e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6b57e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b57e-109">HRESULT</span></span>|<span data-ttu-id="6b57e-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="6b57e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b57e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b57e-111">S_OK</span></span>|<span data-ttu-id="6b57e-112">`celt` элементы пропущены.</span><span class="sxs-lookup"><span data-stu-id="6b57e-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="6b57e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6b57e-113">S_FALSE</span></span>|<span data-ttu-id="6b57e-114">`celt`Пропущено меньше элементов, что означает, что больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="6b57e-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b57e-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6b57e-115">Remarks</span></span>  

 <span data-ttu-id="6b57e-116">Новая позиции курсора перечислителя — (Текущая позиции) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="6b57e-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b57e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="6b57e-117">Requirements</span></span>  

 <span data-ttu-id="6b57e-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b57e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b57e-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b57e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b57e-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b57e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b57e-121">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b57e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b57e-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6b57e-122">See also</span></span>

- [<span data-ttu-id="6b57e-123">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="6b57e-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="6b57e-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6b57e-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
