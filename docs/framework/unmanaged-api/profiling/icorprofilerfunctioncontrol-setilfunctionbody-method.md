---
title: Метод ICorProfilerFunctionControl::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: a6b24fd59a183a4a59b117663772417d55cc67db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503148"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="8cc10-102">Метод ICorProfilerFunctionControl::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="8cc10-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="8cc10-103">Заменяет тело метода на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="8cc10-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cc10-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cc10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cc10-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="8cc10-106">[in] Общий размер нового кода CIL, включая заголовок и все структуры после тела.</span><span class="sxs-lookup"><span data-stu-id="8cc10-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="8cc10-107">[in] Указатель на новый заголовок на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="8cc10-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cc10-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8cc10-108">Return Value</span></span>  
 <span data-ttu-id="8cc10-109">Этот метод возвращает следующие специфичные результаты HRESULT.</span><span class="sxs-lookup"><span data-stu-id="8cc10-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="8cc10-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8cc10-110">HRESULT</span></span>|<span data-ttu-id="8cc10-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8cc10-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8cc10-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cc10-112">S_OK</span></span>|<span data-ttu-id="8cc10-113">Замена выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="8cc10-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cc10-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="8cc10-114">Remarks</span></span>  
 <span data-ttu-id="8cc10-115">В отличие от метода [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) `SetILFunctionBody` метод управляет памятью, необходимой для нового тела CIL.</span><span class="sxs-lookup"><span data-stu-id="8cc10-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="8cc10-116">Это означает, что тело CIL, предоставленное профилировщиком, не должно выделяться с помощью интерфейса [IMethodMalloc](imethodmalloc-interface.md) или выделено в определенном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="8cc10-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="8cc10-117">Его можно разместить в любой куче.</span><span class="sxs-lookup"><span data-stu-id="8cc10-117">It can be allocated on any heap.</span></span> <span data-ttu-id="8cc10-118">Профилировщик может освободить память, используемую для его тела CIL после `SetILFunctionBody` возврата.</span><span class="sxs-lookup"><span data-stu-id="8cc10-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cc10-119">Требования</span><span class="sxs-lookup"><span data-stu-id="8cc10-119">Requirements</span></span>  
 <span data-ttu-id="8cc10-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cc10-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cc10-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8cc10-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8cc10-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cc10-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cc10-123">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cc10-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc10-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc10-124">See also</span></span>

- [<span data-ttu-id="8cc10-125">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="8cc10-125">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
