---
title: Метод ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: 18298c4c726d7d850e67afbf82ca77b7511d8917
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722599"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="cc8ce-102">Метод ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="cc8ce-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="cc8ce-103">Возвращает идентификатор текущего потока, если он является управляемым потоком.</span><span class="sxs-lookup"><span data-stu-id="cc8ce-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc8ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc8ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc8ce-105">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="cc8ce-106">заполняет Указатель на возвращенный идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="cc8ce-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc8ce-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cc8ce-107">Remarks</span></span>  

 <span data-ttu-id="cc8ce-108">Если текущий поток является внутренним потоком среды выполнения или другим неуправляемым потоком, `GetCurrentThreadID` возвращает CORPROF_E_NOT_MANAGED_THREAD как HRESULT, а возвращаемое значение `pThreadId` параметра будет равно null.</span><span class="sxs-lookup"><span data-stu-id="cc8ce-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc8ce-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cc8ce-109">Requirements</span></span>  

 <span data-ttu-id="cc8ce-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc8ce-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8ce-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc8ce-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc8ce-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc8ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc8ce-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc8ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8ce-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc8ce-114">See also</span></span>

- [<span data-ttu-id="cc8ce-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cc8ce-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
