---
title: Интерфейс ICorDebugStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687519"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="1fac6-102">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="1fac6-102">ICorDebugStackWalk Interface</span></span>

<span data-ttu-id="1fac6-103">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="1fac6-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fac6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1fac6-104">Methods</span></span>  
  
|<span data-ttu-id="1fac6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1fac6-105">Method</span></span>|<span data-ttu-id="1fac6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1fac6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fac6-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="1fac6-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="1fac6-108">Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекте.</span><span class="sxs-lookup"><span data-stu-id="1fac6-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="1fac6-109">Метод SetContext</span><span class="sxs-lookup"><span data-stu-id="1fac6-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="1fac6-110">Задает `ICorDebugStackWalk` для текущего контекста объекта допустимый контекст для потока.</span><span class="sxs-lookup"><span data-stu-id="1fac6-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="1fac6-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="1fac6-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="1fac6-112">Перемещает `ICorDebugStackWalk` объект на следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="1fac6-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="1fac6-113">Метод GetFrame</span><span class="sxs-lookup"><span data-stu-id="1fac6-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="1fac6-114">Возвращает текущий кадр в `ICorDebugStackWalk` объекте.</span><span class="sxs-lookup"><span data-stu-id="1fac6-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fac6-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1fac6-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fac6-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="1fac6-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fac6-117">Требования</span><span class="sxs-lookup"><span data-stu-id="1fac6-117">Requirements</span></span>  

 <span data-ttu-id="1fac6-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fac6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fac6-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fac6-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fac6-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fac6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fac6-121">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fac6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fac6-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1fac6-122">See also</span></span>

- [<span data-ttu-id="1fac6-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1fac6-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1fac6-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="1fac6-124">Debugging</span></span>](index.md)
