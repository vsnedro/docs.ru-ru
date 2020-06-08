---
title: Метод ICorProfilerCallback::JITInlining
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 13ce44c9c7a04b870278bc8926dd9fe5daf10bc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500017"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="1a557-102">Метод ICorProfilerCallback::JITInlining</span><span class="sxs-lookup"><span data-stu-id="1a557-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="1a557-103">Уведомляет профилировщик о том, что JIT-компилятор собирается вставить функцию в строку с другой функцией.</span><span class="sxs-lookup"><span data-stu-id="1a557-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a557-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a557-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a557-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a557-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="1a557-106">окне Идентификатор функции, в которую `calleeId` будет вставлена функция.</span><span class="sxs-lookup"><span data-stu-id="1a557-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="1a557-107">окне Идентификатор вставляемой функции.</span><span class="sxs-lookup"><span data-stu-id="1a557-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="1a557-108">[out] `true` значение, чтобы разрешить вставку; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="1a557-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a557-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a557-109">Remarks</span></span>  
 <span data-ttu-id="1a557-110">Профилировщик может задать `pfShouldInline` для значение `false` , чтобы предотвратить `calleeId` вставку функции в `callerId` функцию.</span><span class="sxs-lookup"><span data-stu-id="1a557-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="1a557-111">Кроме того, профилировщик может глобально отключить встроенную вставку, используя значение COR_PRF_DISABLE_INLINING перечисления [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1a557-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="1a557-112">Встроенные функции не вызывают события для входа или вставки.</span><span class="sxs-lookup"><span data-stu-id="1a557-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="1a557-113">Таким образом, профилировщик должен установить в значение, чтобы `pfShouldInline` `false` получить точную граф вызовов.</span><span class="sxs-lookup"><span data-stu-id="1a557-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="1a557-114">Установка `pfShouldInline` значения `false` влияет на производительность, так как встроенная вставка обычно увеличивает скорость и сокращает число отдельных событий JIT-компиляции для метода inserted.</span><span class="sxs-lookup"><span data-stu-id="1a557-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a557-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1a557-115">Requirements</span></span>  
 <span data-ttu-id="1a557-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a557-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a557-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a557-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a557-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a557-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a557-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a557-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a557-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1a557-120">See also</span></span>

- [<span data-ttu-id="1a557-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1a557-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
