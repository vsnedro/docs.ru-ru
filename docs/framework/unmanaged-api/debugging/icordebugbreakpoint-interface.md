---
title: Интерфейс ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: b92c3d3328c657762ed002155ef4947a9292b19e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894732"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="9ecae-102">Интерфейс ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9ecae-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="9ecae-103">Представляет точку останова в функции или точку контрольного значения.</span><span class="sxs-lookup"><span data-stu-id="9ecae-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ecae-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9ecae-104">Methods</span></span>  
  
|<span data-ttu-id="9ecae-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9ecae-105">Method</span></span>|<span data-ttu-id="9ecae-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9ecae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ecae-107">Метод Activate</span><span class="sxs-lookup"><span data-stu-id="9ecae-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="9ecae-108">Задает активное состояние этого `ICorDebugBreakpoint`объекта.</span><span class="sxs-lookup"><span data-stu-id="9ecae-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="9ecae-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="9ecae-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="9ecae-110">Возвращает значение, указывающее, является ли `ICorDebugBreakpoint` этот объект активным.</span><span class="sxs-lookup"><span data-stu-id="9ecae-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ecae-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ecae-111">Remarks</span></span>  
 <span data-ttu-id="9ecae-112">Точки останова не поддерживают непосредственно условные выражения.</span><span class="sxs-lookup"><span data-stu-id="9ecae-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="9ecae-113">Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9ecae-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="9ecae-114">Интерфейс ICorDebugFunctionBreakpoint расширяется `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="9ecae-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ecae-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9ecae-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ecae-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9ecae-116">Requirements</span></span>  
 <span data-ttu-id="9ecae-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ecae-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ecae-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ecae-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ecae-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ecae-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ecae-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ecae-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecae-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ecae-121">See also</span></span>

- [<span data-ttu-id="9ecae-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9ecae-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
