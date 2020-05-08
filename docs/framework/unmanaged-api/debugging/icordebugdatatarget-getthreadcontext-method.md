---
title: Метод ICorDebugDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 79708aa5a2abcb8d7465f82a8beb918484c193b9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976555"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="25ad5-102">Метод ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="25ad5-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="25ad5-103">Возвращает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="25ad5-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25ad5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25ad5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25ad5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="25ad5-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="25ad5-106">окне Идентификатор потока, контекст которого должен быть получен.</span><span class="sxs-lookup"><span data-stu-id="25ad5-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="25ad5-107">Идентификатор определяется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="25ad5-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="25ad5-108">окне Побитовое сочетание флагов, зависящих от платформы, которые указывают, какие части контекста должны считываться.</span><span class="sxs-lookup"><span data-stu-id="25ad5-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="25ad5-109">[входной] Размер `pContext`.</span><span class="sxs-lookup"><span data-stu-id="25ad5-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="25ad5-110">заполняет Буфер, в котором будет храниться контекст потока.</span><span class="sxs-lookup"><span data-stu-id="25ad5-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25ad5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="25ad5-111">Remarks</span></span>  
 <span data-ttu-id="25ad5-112">На платформах Windows `pContext` должна быть `CONTEXT` структура (определенная в Winnt. h), подходящая для типа компьютера, указанного в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="25ad5-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="25ad5-113">`contextFlags`должны иметь те же значения, что `ContextFlags` и поле `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="25ad5-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="25ad5-114">`CONTEXT` Структура зависит от конкретного процессора; Дополнительные сведения см. в файле WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="25ad5-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25ad5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="25ad5-115">Requirements</span></span>  
 <span data-ttu-id="25ad5-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25ad5-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ad5-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25ad5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25ad5-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25ad5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25ad5-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25ad5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ad5-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="25ad5-120">See also</span></span>

- [<span data-ttu-id="25ad5-121">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="25ad5-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="25ad5-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="25ad5-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="25ad5-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="25ad5-123">Debugging</span></span>](index.md)
