---
title: Интерфейс ICorDebugProcessEnum
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
ms.openlocfilehash: 31f26a40294857701b151cd2fce35b061da28238
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732532"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="27f58-102">Интерфейс ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="27f58-102">ICorDebugProcessEnum Interface</span></span>

<span data-ttu-id="27f58-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugProcess массивы.</span><span class="sxs-lookup"><span data-stu-id="27f58-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27f58-104">Методы</span><span class="sxs-lookup"><span data-stu-id="27f58-104">Methods</span></span>  
  
|<span data-ttu-id="27f58-105">Метод</span><span class="sxs-lookup"><span data-stu-id="27f58-105">Method</span></span>|<span data-ttu-id="27f58-106">Описание</span><span class="sxs-lookup"><span data-stu-id="27f58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27f58-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="27f58-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="27f58-108">Возвращает указанное количество `ICorDebugProcess` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="27f58-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27f58-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="27f58-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27f58-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="27f58-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27f58-111">Требования</span><span class="sxs-lookup"><span data-stu-id="27f58-111">Requirements</span></span>  

 <span data-ttu-id="27f58-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27f58-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27f58-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27f58-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27f58-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27f58-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27f58-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27f58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f58-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="27f58-116">See also</span></span>

- [<span data-ttu-id="27f58-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="27f58-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
