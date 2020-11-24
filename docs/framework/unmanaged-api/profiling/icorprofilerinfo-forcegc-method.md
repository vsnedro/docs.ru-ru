---
title: Метод ICorProfilerInfo::ForceGC
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: 75f2db5e5489f02dcae3db0c3e6af19c922e0745
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669202"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="ff84c-102">Метод ICorProfilerInfo::ForceGC</span><span class="sxs-lookup"><span data-stu-id="ff84c-102">ICorProfilerInfo::ForceGC Method</span></span>

<span data-ttu-id="ff84c-103">Принудительное выполнение сборки мусора в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="ff84c-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff84c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff84c-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ff84c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff84c-105">Remarks</span></span>  

 <span data-ttu-id="ff84c-106">`ForceGC`Метод должен вызываться только из потока, который никогда не выполнял управляемый код и не имеет обратных вызовов профилировщика в стеке.</span><span class="sxs-lookup"><span data-stu-id="ff84c-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="ff84c-107">Наиболее удобной реализацией является создание отдельного потока в профилировщике, который вызывает `ForceGC` при получении сигнала.</span><span class="sxs-lookup"><span data-stu-id="ff84c-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff84c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ff84c-108">Requirements</span></span>  

 <span data-ttu-id="ff84c-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff84c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff84c-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff84c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff84c-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff84c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff84c-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff84c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff84c-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff84c-113">See also</span></span>

- [<span data-ttu-id="ff84c-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ff84c-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
