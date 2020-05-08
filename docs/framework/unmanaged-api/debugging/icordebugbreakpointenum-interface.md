---
title: Интерфейс ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: e391a02571481d75ce88ae3f3b2b6421705d661c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894702"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="0c557-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="0c557-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="0c557-103">Реализует методы ICorDebugEnum и перечисляет Икордебугбреакпоинт массивы.</span><span class="sxs-lookup"><span data-stu-id="0c557-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c557-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0c557-104">Methods</span></span>  
  
|<span data-ttu-id="0c557-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0c557-105">Method</span></span>|<span data-ttu-id="0c557-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0c557-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c557-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0c557-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="0c557-108">Возвращает указанное количество `ICorDebugBreakpoint` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="0c557-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c557-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c557-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c557-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0c557-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c557-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0c557-111">Requirements</span></span>  
 <span data-ttu-id="0c557-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c557-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c557-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c557-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c557-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c557-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c557-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c557-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c557-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0c557-116">See also</span></span>

- [<span data-ttu-id="0c557-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0c557-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
