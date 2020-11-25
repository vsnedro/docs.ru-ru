---
title: Интерфейс ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
ms.openlocfilehash: 5165ef081aad849c11747807d8cc76b2df0a6c74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729321"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="fe6da-102">Интерфейс ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="fe6da-102">ICorDebugThread Interface</span></span>

<span data-ttu-id="fe6da-103">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="fe6da-103">Represents a thread in a process.</span></span> <span data-ttu-id="fe6da-104">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="fe6da-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe6da-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fe6da-105">Methods</span></span>  
  
|<span data-ttu-id="fe6da-106">Метод</span><span class="sxs-lookup"><span data-stu-id="fe6da-106">Method</span></span>|<span data-ttu-id="fe6da-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fe6da-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe6da-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="fe6da-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="fe6da-109">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="fe6da-109">This method is not implemented.</span></span> <span data-ttu-id="fe6da-110">Не используйте его.</span><span class="sxs-lookup"><span data-stu-id="fe6da-110">Do not use it.</span></span>|  
|[<span data-ttu-id="fe6da-111">Метод CreateEval</span><span class="sxs-lookup"><span data-stu-id="fe6da-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="fe6da-112">Создает объект ICorDebugEval, который работает с этим объектом `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-113">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="fe6da-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="fe6da-114">Создает объект ICorDebugStepper, позволяющий пошаговое выполнение активного кадра в этом объекте `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-115">Метод EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="fe6da-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="fe6da-116">Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в этом `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-117">Метод GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="fe6da-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="fe6da-118">Возвращает указатель интерфейса на активный ICorDebugChain для этого объекта `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-119">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="fe6da-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="fe6da-120">Получает указатель интерфейса на активный объект ICorDebugFrame для этого `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-121">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="fe6da-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="fe6da-122">Возвращает указатель интерфейса на домен приложения, в котором выполняется в `ICorDebugThread` данный момент.</span><span class="sxs-lookup"><span data-stu-id="fe6da-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="fe6da-123">Метод GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="fe6da-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="fe6da-124">Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="fe6da-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="fe6da-125">Метод GetDebugState</span><span class="sxs-lookup"><span data-stu-id="fe6da-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="fe6da-126">Возвращает значение Кордебугсреадстате, описывающее текущее состояние отладки этого объекта `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-127">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="fe6da-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="fe6da-128">Возвращает текущий обработчик для активной части этого объекта `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-129">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="fe6da-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="fe6da-130">Возвращает идентификатор текущей операционной системы активной части `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-131">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="fe6da-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="fe6da-132">Возвращает указатель интерфейса на поток среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fe6da-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="fe6da-133">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="fe6da-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="fe6da-134">Возвращает указатель интерфейса для процесса, частью которого является эта `ICorDebugThread` форма.</span><span class="sxs-lookup"><span data-stu-id="fe6da-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="fe6da-135">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="fe6da-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="fe6da-136">Возвращает указатель интерфейса на набор регистров, связанный с этим `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-137">Метод GetUserState</span><span class="sxs-lookup"><span data-stu-id="fe6da-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="fe6da-138">Возвращает побитовое сочетание значений Кордебугусерстате, описывающих текущее состояние этого объекта `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fe6da-139">Метод SetDebugState</span><span class="sxs-lookup"><span data-stu-id="fe6da-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="fe6da-140">Задает побитовое сочетание `CorDebugThreadState` значений, описывающих состояние отладки этого объекта `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fe6da-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe6da-141">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fe6da-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe6da-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="fe6da-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe6da-143">Требования</span><span class="sxs-lookup"><span data-stu-id="fe6da-143">Requirements</span></span>  

 <span data-ttu-id="fe6da-144">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe6da-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe6da-145">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe6da-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe6da-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe6da-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe6da-147">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe6da-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6da-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fe6da-148">See also</span></span>

- [<span data-ttu-id="fe6da-149">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fe6da-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
