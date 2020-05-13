---
title: Метод ICorDebugStackWalk::GetFrame
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
ms.openlocfilehash: 5f80125a67e634dda05b9427b5f46db8f21b29f8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379199"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="b28c8-102">Метод ICorDebugStackWalk::GetFrame</span><span class="sxs-lookup"><span data-stu-id="b28c8-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="b28c8-103">Возвращает текущий кадр в объекте [икордебугстакквалк](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b28c8-103">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b28c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b28c8-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="b28c8-106">окне Указатель на адрес созданного объекта Frame, представляющий текущий кадр в стеке.</span><span class="sxs-lookup"><span data-stu-id="b28c8-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28c8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b28c8-107">Return Value</span></span>  
 <span data-ttu-id="b28c8-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b28c8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b28c8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b28c8-109">HRESULT</span></span>|<span data-ttu-id="b28c8-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b28c8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b28c8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b28c8-111">S_OK</span></span>|<span data-ttu-id="b28c8-112">Среда выполнения успешно вернула текущий кадр.</span><span class="sxs-lookup"><span data-stu-id="b28c8-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="b28c8-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b28c8-113">E_FAIL</span></span>|<span data-ttu-id="b28c8-114">Текущий кадр не был возвращен.</span><span class="sxs-lookup"><span data-stu-id="b28c8-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="b28c8-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b28c8-115">S_FALSE</span></span>|<span data-ttu-id="b28c8-116">Текущий кадр является машинным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="b28c8-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="b28c8-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b28c8-117">E_INVALIDARG</span></span>|<span data-ttu-id="b28c8-118">Параметр `pFrame` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b28c8-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="b28c8-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="b28c8-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="b28c8-120">Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.</span><span class="sxs-lookup"><span data-stu-id="b28c8-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b28c8-121">Исключения</span><span class="sxs-lookup"><span data-stu-id="b28c8-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b28c8-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b28c8-122">Remarks</span></span>  
 <span data-ttu-id="b28c8-123">`ICorDebugStackWalk`Возвращает только фактические кадры стека.</span><span class="sxs-lookup"><span data-stu-id="b28c8-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="b28c8-124">Используйте метод [ICorDebugThread3:: жетактивеинтерналфрамес](icordebugthread3-getactiveinternalframes-method.md) для возврата внутренних кадров.</span><span class="sxs-lookup"><span data-stu-id="b28c8-124">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="b28c8-125">(Внутренние кадры — это структуры данных, помещаемые в стек средой выполнения для хранения временных данных.)</span><span class="sxs-lookup"><span data-stu-id="b28c8-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28c8-126">Требования</span><span class="sxs-lookup"><span data-stu-id="b28c8-126">Requirements</span></span>  
 <span data-ttu-id="b28c8-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28c8-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28c8-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b28c8-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b28c8-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b28c8-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b28c8-130">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28c8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28c8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b28c8-131">See also</span></span>

- [<span data-ttu-id="b28c8-132">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="b28c8-132">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="b28c8-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b28c8-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b28c8-134">Отладка</span><span class="sxs-lookup"><span data-stu-id="b28c8-134">Debugging</span></span>](index.md)
