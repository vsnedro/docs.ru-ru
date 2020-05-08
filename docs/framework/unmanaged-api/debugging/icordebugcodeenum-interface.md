---
title: Интерфейс ICorDebugCodeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
ms.openlocfilehash: cce0efa925683b5361a5422112db3f8231e2dfb4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893278"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="fe564-102">Интерфейс ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="fe564-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="fe564-103">Реализует методы "ICorDebugEnum" и перечисляет массивы ICorDebugCode.</span><span class="sxs-lookup"><span data-stu-id="fe564-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe564-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fe564-104">Methods</span></span>  
  
|<span data-ttu-id="fe564-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fe564-105">Method</span></span>|<span data-ttu-id="fe564-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fe564-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe564-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="fe564-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="fe564-108">Возвращает указанное количество `ICorDebugCode` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="fe564-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe564-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe564-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe564-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="fe564-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe564-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fe564-111">Requirements</span></span>  
 <span data-ttu-id="fe564-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe564-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe564-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe564-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe564-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe564-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe564-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe564-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe564-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fe564-116">See also</span></span>

- [<span data-ttu-id="fe564-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fe564-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
