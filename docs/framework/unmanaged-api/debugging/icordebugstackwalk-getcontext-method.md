---
title: Метод ICorDebugStackWalk::GetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 927f2077b4bb71177c24816774d06643ebdaa922
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711966"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="922f8-102">Метод ICorDebugStackWalk::GetContext</span><span class="sxs-lookup"><span data-stu-id="922f8-102">ICorDebugStackWalk::GetContext Method</span></span>

<span data-ttu-id="922f8-103">Возвращает контекст для текущего кадра в объекте [икордебугстакквалк](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="922f8-103">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="922f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="922f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="922f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="922f8-105">Parameters</span></span>  

 `contextFlags`  
 <span data-ttu-id="922f8-106">окне Флаги, указывающие запрошенное содержимое буфера контекста (определенного в WinNT. h).</span><span class="sxs-lookup"><span data-stu-id="922f8-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="922f8-107">окне Выделенный размер буфера контекста.</span><span class="sxs-lookup"><span data-stu-id="922f8-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="922f8-108">заполняет Фактический размер контекста.</span><span class="sxs-lookup"><span data-stu-id="922f8-108">[out] The actual size of the context.</span></span> <span data-ttu-id="922f8-109">Это значение должно быть меньше или равно размеру буфера контекста.</span><span class="sxs-lookup"><span data-stu-id="922f8-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="922f8-110">заполняет Буфер контекста.</span><span class="sxs-lookup"><span data-stu-id="922f8-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="922f8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="922f8-111">Return Value</span></span>  

 <span data-ttu-id="922f8-112">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="922f8-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="922f8-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="922f8-113">HRESULT</span></span>|<span data-ttu-id="922f8-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="922f8-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="922f8-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="922f8-115">S_OK</span></span>|<span data-ttu-id="922f8-116">Контекст для текущего кадра успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="922f8-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="922f8-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="922f8-117">E_FAIL</span></span>|<span data-ttu-id="922f8-118">Не удалось вернуть контекст.</span><span class="sxs-lookup"><span data-stu-id="922f8-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="922f8-119">HRESULT_FROM_WIN32 (БУФЕР ERROR_INSUFFICIENT)</span><span class="sxs-lookup"><span data-stu-id="922f8-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="922f8-120">Буфер контекста слишком мал.</span><span class="sxs-lookup"><span data-stu-id="922f8-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="922f8-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="922f8-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="922f8-122">Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.</span><span class="sxs-lookup"><span data-stu-id="922f8-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="922f8-123">Исключения</span><span class="sxs-lookup"><span data-stu-id="922f8-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="922f8-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="922f8-124">Remarks</span></span>  

 <span data-ttu-id="922f8-125">Поскольку при очистке восстанавливаются только подмножество регистров, например непостоянные регистры, контекст может точно не соответствовать состоянию регистрации во время вызова.</span><span class="sxs-lookup"><span data-stu-id="922f8-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="922f8-126">Требования</span><span class="sxs-lookup"><span data-stu-id="922f8-126">Requirements</span></span>  

 <span data-ttu-id="922f8-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="922f8-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="922f8-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="922f8-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="922f8-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="922f8-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="922f8-130">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="922f8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="922f8-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="922f8-131">See also</span></span>

- [<span data-ttu-id="922f8-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="922f8-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="922f8-133">Отладка</span><span class="sxs-lookup"><span data-stu-id="922f8-133">Debugging</span></span>](index.md)
