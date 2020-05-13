---
title: Интерфейс ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: 9c2771d1338943406921447d96dd9a8748153a36
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209634"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="66a04-102">Интерфейс ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="66a04-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="66a04-103">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="66a04-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66a04-104">Методы</span><span class="sxs-lookup"><span data-stu-id="66a04-104">Methods</span></span>  
  
|<span data-ttu-id="66a04-105">Метод</span><span class="sxs-lookup"><span data-stu-id="66a04-105">Method</span></span>|<span data-ttu-id="66a04-106">Описание</span><span class="sxs-lookup"><span data-stu-id="66a04-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66a04-107">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="66a04-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="66a04-108">Получает объект ICorDebugStepper, выполняющий пошаговые операции по отношению к этому `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="66a04-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="66a04-109">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="66a04-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="66a04-110">Возвращает указатель на объект `ICorDebugFrame` в текущей цепочке, который вызвал этот кадр, или возвращает значение null, если это внутренняя рамка в цепочке.</span><span class="sxs-lookup"><span data-stu-id="66a04-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="66a04-111">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="66a04-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="66a04-112">Возвращает указатель на объект `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это самый внешний кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="66a04-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="66a04-113">Метод GetChain</span><span class="sxs-lookup"><span data-stu-id="66a04-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="66a04-114">Возвращает указатель на ICorDebugChain, частью которого `ICorDebugFrame` является.</span><span class="sxs-lookup"><span data-stu-id="66a04-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="66a04-115">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="66a04-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="66a04-116">Возвращает указатель на ICorDebugCode, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="66a04-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="66a04-117">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="66a04-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="66a04-118">Возвращает указатель на ICorDebugFunction, содержащий код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="66a04-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="66a04-119">Метод GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="66a04-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="66a04-120">Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="66a04-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="66a04-121">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="66a04-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="66a04-122">Возвращает диапазон абсолютных адресов кадра стека, представленного этим объектом `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="66a04-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66a04-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="66a04-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66a04-124">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="66a04-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66a04-125">Требования</span><span class="sxs-lookup"><span data-stu-id="66a04-125">Requirements</span></span>  
 <span data-ttu-id="66a04-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66a04-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a04-127">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66a04-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66a04-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66a04-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66a04-129">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a04-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a04-130">См. также</span><span class="sxs-lookup"><span data-stu-id="66a04-130">See also</span></span>

- [<span data-ttu-id="66a04-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="66a04-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
