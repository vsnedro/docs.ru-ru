---
title: Интерфейс ICorDebugStepperEnum
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
ms.openlocfilehash: facea5cd7f0b0e0e6c0b1049e87a2355f1d3965a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697172"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="312f2-102">Интерфейс ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="312f2-102">ICorDebugStepperEnum Interface</span></span>

<span data-ttu-id="312f2-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugStepper.</span><span class="sxs-lookup"><span data-stu-id="312f2-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="312f2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="312f2-104">Methods</span></span>  
  
|<span data-ttu-id="312f2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="312f2-105">Method</span></span>|<span data-ttu-id="312f2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="312f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="312f2-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="312f2-107">Next Method</span></span>](icordebugstepperenum-next-method.md)|<span data-ttu-id="312f2-108">Возвращает указанное количество `ICorDebugStepper` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="312f2-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="312f2-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="312f2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="312f2-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="312f2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="312f2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="312f2-111">Requirements</span></span>  

 <span data-ttu-id="312f2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="312f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="312f2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="312f2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="312f2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="312f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="312f2-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="312f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312f2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="312f2-116">See also</span></span>

- [<span data-ttu-id="312f2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="312f2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
