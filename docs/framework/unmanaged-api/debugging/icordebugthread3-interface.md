---
title: Интерфейс ICorDebugThread3
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 015d0061e5be5bbc212243ca06f1d165abe4496a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729308"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="a82a9-102">Интерфейс ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="a82a9-102">ICorDebugThread3 Interface</span></span>

<span data-ttu-id="a82a9-103">Предоставляет точку входа для [икордебугстакквалк](icordebugstackwalk-interface.md) и соответствующих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a82a9-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a82a9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a82a9-104">Methods</span></span>  
  
|<span data-ttu-id="a82a9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a82a9-105">Method</span></span>|<span data-ttu-id="a82a9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a82a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a82a9-107">Метод CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="a82a9-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="a82a9-108">Создает объект [икордебугстакквалк](icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="a82a9-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="a82a9-109">Метод GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="a82a9-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="a82a9-110">Возвращает массив внутренних кадров (объектов[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) в стеке.</span><span class="sxs-lookup"><span data-stu-id="a82a9-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a82a9-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a82a9-111">Remarks</span></span>  

 <span data-ttu-id="a82a9-112">`ICorDebugThread3` является логическим расширением для интерфейса ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="a82a9-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a82a9-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a82a9-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a82a9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a82a9-114">Requirements</span></span>  

 <span data-ttu-id="a82a9-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a82a9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82a9-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a82a9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a82a9-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a82a9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a82a9-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a82a9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82a9-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a82a9-119">See also</span></span>

- [<span data-ttu-id="a82a9-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a82a9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a82a9-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="a82a9-121">Debugging</span></span>](index.md)
