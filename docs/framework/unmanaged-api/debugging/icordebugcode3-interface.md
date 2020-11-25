---
title: Интерфейс ICorDebugCode3
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: 609cd557db71fac53aadf613534a23e988b14bde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720763"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="d194b-102">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="d194b-102">ICorDebugCode3 Interface</span></span>

<span data-ttu-id="d194b-103">Предоставляет метод, который расширяет "ICorDebugCode" и "ICorDebugCode2" для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="d194b-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d194b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d194b-104">Methods</span></span>  
  
|<span data-ttu-id="d194b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d194b-105">Method</span></span>|<span data-ttu-id="d194b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d194b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d194b-107">Метод GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="d194b-107">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="d194b-108">Для указанного смещения IL получает машинные смещения, в которых должна быть помещена точка останова, чтобы отладчик мог получить возвращаемое значение из функции.</span><span class="sxs-lookup"><span data-stu-id="d194b-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d194b-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d194b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d194b-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d194b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d194b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d194b-111">Requirements</span></span>  

 <span data-ttu-id="d194b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d194b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d194b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d194b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d194b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d194b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d194b-115">**.NET Framework версии:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d194b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d194b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d194b-116">See also</span></span>

- [<span data-ttu-id="d194b-117">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="d194b-117">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
- [<span data-ttu-id="d194b-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d194b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
