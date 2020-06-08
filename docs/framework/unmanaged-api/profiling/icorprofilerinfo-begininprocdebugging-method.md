---
title: Метод ICorProfilerInfo::BeginInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: f0b118ef109d0adb17a28b60c091390b8e4280c9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498665"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="f0fae-102">Метод ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="f0fae-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="f0fae-103">Инициализирует поддержку внутрипроцессного отладки.</span><span class="sxs-lookup"><span data-stu-id="f0fae-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="f0fae-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="f0fae-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0fae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0fae-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0fae-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0fae-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="f0fae-107">окне Установите это значение, чтобы `true` инициализировать поддержку отладки только для текущего потока; установите его в значение `false` , чтобы инициализировать поддержку отладки для всех потоков.</span><span class="sxs-lookup"><span data-stu-id="f0fae-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="f0fae-108">заполняет Указатель на возвращаемое значение, идентифицирующее сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="f0fae-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0fae-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0fae-109">Remarks</span></span>  
 <span data-ttu-id="f0fae-110">Службы отладки CLR поддерживали ограниченную внутрипроцессную отладку в .NET Framework версиях 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="f0fae-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="f0fae-111">В процессе отладки с помощью профилировщика можно использовать части проверки для API отладки.</span><span class="sxs-lookup"><span data-stu-id="f0fae-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f0fae-112">Однако из-за отзывов клиентов внутрипроцессный процесс отладки был удален из .NET Framework в версии 2,0 и заменен набором функциональных возможностей, которые более подробно описаны в API профилирования.</span><span class="sxs-lookup"><span data-stu-id="f0fae-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0fae-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f0fae-113">Requirements</span></span>  
 <span data-ttu-id="f0fae-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0fae-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0fae-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0fae-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0fae-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0fae-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0fae-117">**Версия .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="f0fae-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fae-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f0fae-118">See also</span></span>

- [<span data-ttu-id="f0fae-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f0fae-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
