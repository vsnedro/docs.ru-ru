---
title: Интерфейс ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 6619b8888588341f23a93b83865cd2e75cc9b3db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712018"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="376a1-102">Интерфейс ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="376a1-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>

<span data-ttu-id="376a1-103">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="376a1-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="376a1-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="376a1-104">Remarks</span></span>  

 <span data-ttu-id="376a1-105">`ICorDebugRuntimeUnwindableFrame` — Это специализированная версия интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="376a1-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="376a1-106">Он используется неуправляемыми методами, требующими от среды выполнения очистки кадра в текущем стеке.</span><span class="sxs-lookup"><span data-stu-id="376a1-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="376a1-107">Существующие правила очистки не работают, так как они не используют JIT-скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="376a1-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="376a1-108">Когда отладчик видит неотображаемый кадр, он должен использовать метод [икордебугстакквалк:: Next](icordebugstackwalk-next-method.md) для его очистки, но должен выполнить проверку.</span><span class="sxs-lookup"><span data-stu-id="376a1-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="376a1-109">Когда отладчик получает объект `ICorDebugRuntimeUnwindableFrame` , он может вызвать метод [икордебугстакквалк:: oncontext](icordebugstackwalk-getcontext-method.md) для получения контекста кадра.</span><span class="sxs-lookup"><span data-stu-id="376a1-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="376a1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="376a1-110">Requirements</span></span>  

 <span data-ttu-id="376a1-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="376a1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="376a1-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="376a1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="376a1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="376a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="376a1-114">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="376a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="376a1-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="376a1-115">See also</span></span>

- [<span data-ttu-id="376a1-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="376a1-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="376a1-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="376a1-117">Debugging</span></span>](index.md)
