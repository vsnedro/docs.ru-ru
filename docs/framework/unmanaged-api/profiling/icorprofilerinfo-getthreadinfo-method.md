---
title: Метод ICorProfilerInfo::GetThreadInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
ms.openlocfilehash: 532288364b2db1e6be49b9e6f87019b1e41e6866
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497924"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="4b472-102">Метод ICorProfilerInfo::GetThreadInfo</span><span class="sxs-lookup"><span data-stu-id="4b472-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="4b472-103">Возвращает текущее удостоверение потока Win32 для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="4b472-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b472-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b472-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b472-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b472-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="4b472-106">окне Идентификатор потока, для которого необходимо получить текущий идентификатор Win32.</span><span class="sxs-lookup"><span data-stu-id="4b472-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="4b472-107">заполняет Указатель на текущий идентификатор потока Win32 указанного потока.</span><span class="sxs-lookup"><span data-stu-id="4b472-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b472-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4b472-108">Requirements</span></span>  
 <span data-ttu-id="4b472-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b472-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b472-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b472-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b472-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b472-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b472-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b472-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b472-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4b472-113">See also</span></span>

- [<span data-ttu-id="4b472-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="4b472-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
