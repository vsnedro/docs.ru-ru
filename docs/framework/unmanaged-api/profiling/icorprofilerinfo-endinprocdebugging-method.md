---
title: Метод ICorProfilerInfo::EndInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
ms.openlocfilehash: e929c74ba0f1f33ddbb28476b3c9e0a512567ac6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669059"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="13146-102">Метод ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="13146-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>

<span data-ttu-id="13146-103">Завершает работу внутрипроцессного сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="13146-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="13146-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="13146-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13146-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13146-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13146-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="13146-106">Parameters</span></span>  

 `dwProfilerContext`  
 <span data-ttu-id="13146-107">окне Значение, идентифицирующее сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="13146-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="13146-108">Это значение должно совпадать со значением, полученным в методе [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13146-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13146-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="13146-109">Remarks</span></span>  

 <span data-ttu-id="13146-110">Необходимо вызвать метод [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) и в `EndInprocDebugging` том же методе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="13146-110">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="13146-111">Службы отладки CLR поддерживали ограниченную внутрипроцессную отладку в .NET Framework версиях 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="13146-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="13146-112">В процессе отладки с помощью профилировщика можно использовать части проверки для API отладки.</span><span class="sxs-lookup"><span data-stu-id="13146-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="13146-113">Однако из-за отзывов клиентов внутрипроцессный процесс отладки был удален из .NET Framework в версии 2,0 и заменен набором функциональных возможностей, которые более подробно описаны в API профилирования.</span><span class="sxs-lookup"><span data-stu-id="13146-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13146-114">Требования</span><span class="sxs-lookup"><span data-stu-id="13146-114">Requirements</span></span>  

 <span data-ttu-id="13146-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13146-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13146-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13146-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13146-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13146-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13146-118">**Версия .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="13146-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13146-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13146-119">See also</span></span>

- [<span data-ttu-id="13146-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="13146-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
