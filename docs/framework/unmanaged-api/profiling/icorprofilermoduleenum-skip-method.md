---
title: Метод ICorProfilerModuleEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
ms.openlocfilehash: 6a967f9a50b3220e2d5e206503330a2bab764c4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701644"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="c0fbc-102">Метод ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="c0fbc-102">ICorProfilerModuleEnum::Skip Method</span></span>

<span data-ttu-id="c0fbc-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="c0fbc-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0fbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0fbc-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0fbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0fbc-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="c0fbc-106">окне Число пропущенных элементов.</span><span class="sxs-lookup"><span data-stu-id="c0fbc-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0fbc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0fbc-107">Return Value</span></span>  

 <span data-ttu-id="c0fbc-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="c0fbc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c0fbc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0fbc-109">HRESULT</span></span>|<span data-ttu-id="c0fbc-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0fbc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0fbc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0fbc-111">S_OK</span></span>|<span data-ttu-id="c0fbc-112">`celt` элементы пропущены.</span><span class="sxs-lookup"><span data-stu-id="c0fbc-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="c0fbc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c0fbc-113">S_FALSE</span></span>|<span data-ttu-id="c0fbc-114">`celt`Пропущено меньше элементов, что означает, что больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="c0fbc-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0fbc-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c0fbc-115">Remarks</span></span>  

 <span data-ttu-id="c0fbc-116">Новая позиции курсора перечислителя — (Текущая позиции) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="c0fbc-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0fbc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c0fbc-117">Requirements</span></span>  

 <span data-ttu-id="c0fbc-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0fbc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0fbc-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0fbc-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0fbc-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0fbc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0fbc-121">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0fbc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fbc-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0fbc-122">See also</span></span>

- [<span data-ttu-id="c0fbc-123">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c0fbc-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="c0fbc-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="c0fbc-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
