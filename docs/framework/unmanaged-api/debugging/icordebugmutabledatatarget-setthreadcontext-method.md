---
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 558a1ee2eb0ac06213c2ebcebbd5595b69ecc43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695714"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="67015-102">Метод ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="67015-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="67015-103">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="67015-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67015-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67015-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67015-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67015-105">Parameters</span></span>  

 `dwThreadID`  
 <span data-ttu-id="67015-106">[in] Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="67015-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="67015-107">[in] Размер буфера `pContext` для записи.</span><span class="sxs-lookup"><span data-stu-id="67015-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="67015-108">[in] Указатель на байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="67015-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67015-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="67015-109">Remarks</span></span>  

 <span data-ttu-id="67015-110">Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="67015-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="67015-111">Формат записи контекста определяется платформой, указанной в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="67015-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="67015-112">В Windows это структура [контекста](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="67015-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67015-113">Требования</span><span class="sxs-lookup"><span data-stu-id="67015-113">Requirements</span></span>  

 <span data-ttu-id="67015-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67015-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67015-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67015-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67015-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67015-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67015-117">**.NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67015-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67015-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="67015-118">See also</span></span>

- [<span data-ttu-id="67015-119">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="67015-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="67015-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67015-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
