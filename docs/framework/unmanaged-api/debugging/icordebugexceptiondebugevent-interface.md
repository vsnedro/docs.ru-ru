---
title: Интерфейс ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: dfa65aa1b63c996068e75ff1165111d5fcfe77eb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976009"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="fc999-102">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="fc999-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="fc999-103">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="fc999-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc999-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fc999-104">Methods</span></span>  
  
|<span data-ttu-id="fc999-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fc999-105">Method</span></span>|<span data-ttu-id="fc999-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fc999-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc999-107">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="fc999-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="fc999-108">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="fc999-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="fc999-109">Метод GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="fc999-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="fc999-110">Получает указатель собственного интерфейса для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="fc999-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="fc999-111">Метод GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="fc999-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="fc999-112">Получает указатель стека для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="fc999-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc999-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc999-113">Remarks</span></span>  
 <span data-ttu-id="fc999-114">Интерфейс `ICorDebugExceptionDebugEvent` реализуется с помощью следующих типов событий:</span><span class="sxs-lookup"><span data-stu-id="fc999-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="fc999-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="fc999-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="fc999-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="fc999-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="fc999-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="fc999-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="fc999-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="fc999-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="fc999-119">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="fc999-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="fc999-120">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fc999-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc999-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fc999-121">Requirements</span></span>  
 <span data-ttu-id="fc999-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc999-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc999-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc999-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc999-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc999-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc999-125">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc999-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc999-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fc999-126">See also</span></span>

- [<span data-ttu-id="fc999-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fc999-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc999-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="fc999-128">Debugging</span></span>](index.md)
