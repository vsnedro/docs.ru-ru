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
ms.openlocfilehash: 3a820381f1c4605d620d74a5915c3e08de69d9fb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210115"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="f863d-102">Интерфейс ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="f863d-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="f863d-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugProcess массивы.</span><span class="sxs-lookup"><span data-stu-id="f863d-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f863d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f863d-104">Methods</span></span>  
  
|<span data-ttu-id="f863d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f863d-105">Method</span></span>|<span data-ttu-id="f863d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f863d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f863d-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="f863d-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="f863d-108">Возвращает указанное количество `ICorDebugProcess` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="f863d-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f863d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f863d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f863d-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f863d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f863d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f863d-111">Requirements</span></span>  
 <span data-ttu-id="f863d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f863d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f863d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f863d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f863d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f863d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f863d-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f863d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f863d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f863d-116">See also</span></span>

- [<span data-ttu-id="f863d-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f863d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
