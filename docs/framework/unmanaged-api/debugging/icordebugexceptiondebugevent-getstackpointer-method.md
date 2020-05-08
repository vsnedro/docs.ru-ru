---
title: Метод ICorDebugExceptionDebugEvent::GetStackPointer
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 4f84183dfc23ebc0d0fee9feeb21329c217b9cca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976022"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="7e450-102">Метод ICorDebugExceptionDebugEvent::GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="7e450-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="7e450-103">Получает указатель стека для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="7e450-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e450-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e450-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e450-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e450-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="7e450-106">[out] Указатель на адрес указателя стека для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="7e450-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="7e450-107">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="7e450-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e450-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e450-108">Remarks</span></span>  
 <span data-ttu-id="7e450-109">Смысл этого указателя стека зависит от типа события, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7e450-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="7e450-110">Тип события.</span><span class="sxs-lookup"><span data-stu-id="7e450-110">Event type</span></span>|<span data-ttu-id="7e450-111">Смысл значения `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="7e450-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="7e450-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7e450-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e450-113">Указатель стека для фрейма, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="7e450-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="7e450-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7e450-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e450-115">Указатель стека для фрейма пользовательского кода, ближайшего к точке вызванного исключения.</span><span class="sxs-lookup"><span data-stu-id="7e450-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="7e450-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="7e450-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e450-117">Указатель стека для фрейма, содержащего обработчик catch.</span><span class="sxs-lookup"><span data-stu-id="7e450-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="7e450-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="7e450-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e450-119">`pStackPointer` имеет значение **NULL**.</span><span class="sxs-lookup"><span data-stu-id="7e450-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7e450-120">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="7e450-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="7e450-121">Тип события доступен в методе [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7e450-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e450-122">Требования</span><span class="sxs-lookup"><span data-stu-id="7e450-122">Requirements</span></span>  
 <span data-ttu-id="7e450-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e450-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e450-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e450-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e450-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e450-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e450-126">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e450-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e450-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e450-127">See also</span></span>

- [<span data-ttu-id="7e450-128">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7e450-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="7e450-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7e450-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
