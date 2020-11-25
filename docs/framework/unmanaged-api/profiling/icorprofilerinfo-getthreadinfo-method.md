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
ms.openlocfilehash: 516a12b7a4457a0f67da24294ad96fb79d1aa5aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707520"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="21fe0-102">Метод ICorProfilerInfo::GetThreadInfo</span><span class="sxs-lookup"><span data-stu-id="21fe0-102">ICorProfilerInfo::GetThreadInfo Method</span></span>

<span data-ttu-id="21fe0-103">Возвращает текущее удостоверение потока Win32 для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="21fe0-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21fe0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21fe0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21fe0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21fe0-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="21fe0-106">окне Идентификатор потока, для которого необходимо получить текущий идентификатор Win32.</span><span class="sxs-lookup"><span data-stu-id="21fe0-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="21fe0-107">заполняет Указатель на текущий идентификатор потока Win32 указанного потока.</span><span class="sxs-lookup"><span data-stu-id="21fe0-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21fe0-108">Требования</span><span class="sxs-lookup"><span data-stu-id="21fe0-108">Requirements</span></span>  

 <span data-ttu-id="21fe0-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21fe0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21fe0-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21fe0-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21fe0-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21fe0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21fe0-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21fe0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fe0-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="21fe0-113">See also</span></span>

- [<span data-ttu-id="21fe0-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="21fe0-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
