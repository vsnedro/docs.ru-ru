---
title: Интерфейс ICorDebugFunctionBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
ms.openlocfilehash: 6a378e3579ab9ea8d9534a408d0e456373616cad
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213148"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="0cee6-102">Интерфейс ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0cee6-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="0cee6-103">Расширяет интерфейс Икордебугбреакпоинт для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="0cee6-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cee6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0cee6-104">Methods</span></span>  
  
|<span data-ttu-id="0cee6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0cee6-105">Method</span></span>|<span data-ttu-id="0cee6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0cee6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cee6-107">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="0cee6-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="0cee6-108">Возвращает указатель на интерфейс ICorDebugFunction, ссылающийся на функцию, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="0cee6-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="0cee6-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="0cee6-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="0cee6-110">Возвращает смещение точки останова внутри функции.</span><span class="sxs-lookup"><span data-stu-id="0cee6-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cee6-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0cee6-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cee6-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0cee6-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cee6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0cee6-113">Requirements</span></span>  
 <span data-ttu-id="0cee6-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cee6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cee6-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cee6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cee6-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cee6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cee6-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cee6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cee6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0cee6-118">See also</span></span>

- [<span data-ttu-id="0cee6-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0cee6-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
