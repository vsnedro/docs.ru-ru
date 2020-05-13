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
ms.openlocfilehash: a7b0608e85411844828cebea34c0ce5ef5b1bd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379386"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="93d6f-102">Интерфейс ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="93d6f-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="93d6f-103">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="93d6f-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93d6f-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="93d6f-104">Remarks</span></span>  
 <span data-ttu-id="93d6f-105">`ICorDebugRuntimeUnwindableFrame`— Это специализированная версия интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="93d6f-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="93d6f-106">Он используется неуправляемыми методами, требующими от среды выполнения очистки кадра в текущем стеке.</span><span class="sxs-lookup"><span data-stu-id="93d6f-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="93d6f-107">Существующие правила очистки не работают, так как они не используют JIT-скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="93d6f-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="93d6f-108">Когда отладчик видит неотображаемый кадр, он должен использовать метод [икордебугстакквалк:: Next](icordebugstackwalk-next-method.md) для его очистки, но должен выполнить проверку.</span><span class="sxs-lookup"><span data-stu-id="93d6f-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="93d6f-109">Когда отладчик получает объект `ICorDebugRuntimeUnwindableFrame` , он может вызвать метод [икордебугстакквалк:: oncontext](icordebugstackwalk-getcontext-method.md) для получения контекста кадра.</span><span class="sxs-lookup"><span data-stu-id="93d6f-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93d6f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="93d6f-110">Requirements</span></span>  
 <span data-ttu-id="93d6f-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93d6f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93d6f-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93d6f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93d6f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93d6f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93d6f-114">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93d6f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d6f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="93d6f-115">See also</span></span>

- [<span data-ttu-id="93d6f-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="93d6f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="93d6f-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="93d6f-117">Debugging</span></span>](index.md)
