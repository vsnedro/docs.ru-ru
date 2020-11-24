---
title: Метод ICorDebugVirtualUnwinder::GetContext
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: a5a1afa47e52eff7c930698a3354a03d8c62259f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679459"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="a4bd3-102">Метод ICorDebugVirtualUnwinder::GetContext</span><span class="sxs-lookup"><span data-stu-id="a4bd3-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>

<span data-ttu-id="a4bd3-103">Получает текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4bd3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4bd3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4bd3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4bd3-105">Parameters</span></span>  

 `contextFlags`  
 <span data-ttu-id="a4bd3-106">[in] Флаги, указывающие, какие части контекста следует возвращать (определенные в заголовке WinNt.h).</span><span class="sxs-lookup"><span data-stu-id="a4bd3-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="a4bd3-107">[in] Количество байтов в `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a4bd3-108">[out] Указатель на число байтов, фактически записанных в `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="a4bd3-109">[out] Байтовый массив, содержащий текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4bd3-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a4bd3-110">Return Value</span></span>  

 <span data-ttu-id="a4bd3-111">Любое ошибочное значение HRESULT , полученное процессом mscordbi, считается неустранимым и приводит к возврату интерфейсами API ICorDebug значения `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4bd3-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a4bd3-112">Remarks</span></span>  

 <span data-ttu-id="a4bd3-113">Начальное значение аргумента задается `contextBuf` в буфере контекста, возвращаемом путем вызова метода [икордебугстакквалк:: oncontext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a4bd3-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4bd3-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="a4bd3-115">Поскольку очистка может восстановить только подмножество регистров, например только неизменяемые регистры, контекст может не соответствовать в точности состоянию регистра во время фактического вызова метода.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4bd3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a4bd3-116">Requirements</span></span>  

 <span data-ttu-id="a4bd3-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4bd3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4bd3-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4bd3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4bd3-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4bd3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4bd3-120">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4bd3-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bd3-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4bd3-121">See also</span></span>

- [<span data-ttu-id="a4bd3-122">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="a4bd3-122">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a4bd3-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a4bd3-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
