---
title: Метод ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: a7d78daf74d3cc01c2313f092bce53950dbd7bfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681227"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="504b7-102">Метод ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="504b7-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>

<span data-ttu-id="504b7-103">Возвращает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="504b7-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="504b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="504b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="504b7-105">Parameters</span></span>  

 `contextSize`  
 <span data-ttu-id="504b7-106">окне Размер массива в байтах `context` .</span><span class="sxs-lookup"><span data-stu-id="504b7-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="504b7-107">[вход, выход] Массив байтов, образующих `CONTEXT` структуру Win32 для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="504b7-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="504b7-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="504b7-108">Remarks</span></span>  

 <span data-ttu-id="504b7-109">Отладчик должен вызвать эту функцию вместо `GetThreadContext` функции Win32, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="504b7-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="504b7-110">Возвращаемые данные представляют собой `CONTEXT` структуру Win32 для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="504b7-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="504b7-111">Для неконечных кадров клиенты должны проверить, какие регистры являются допустимыми с помощью [ICorDebugRegisterSet:: жетрегистерсаваилабле](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="504b7-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="504b7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="504b7-112">Requirements</span></span>  

 <span data-ttu-id="504b7-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="504b7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="504b7-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="504b7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="504b7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="504b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="504b7-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="504b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504b7-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="504b7-117">See also</span></span>

- [<span data-ttu-id="504b7-118">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="504b7-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="504b7-119">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="504b7-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
