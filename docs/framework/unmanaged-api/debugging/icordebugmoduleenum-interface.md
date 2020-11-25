---
title: Интерфейс ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: 08d16393a04888cd3f1a03fa209a1fceac28520b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724758"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="75ac0-102">Интерфейс ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="75ac0-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="75ac0-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugModule массивы.</span><span class="sxs-lookup"><span data-stu-id="75ac0-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75ac0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="75ac0-104">Methods</span></span>  
  
|<span data-ttu-id="75ac0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="75ac0-105">Method</span></span>|<span data-ttu-id="75ac0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="75ac0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75ac0-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="75ac0-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="75ac0-108">Возвращает указанное количество `ICorDebugModule` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="75ac0-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75ac0-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="75ac0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75ac0-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="75ac0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75ac0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="75ac0-111">Requirements</span></span>  

 <span data-ttu-id="75ac0-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75ac0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75ac0-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75ac0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75ac0-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75ac0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75ac0-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75ac0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ac0-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75ac0-116">See also</span></span>

- [<span data-ttu-id="75ac0-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="75ac0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
