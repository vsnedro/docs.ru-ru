---
title: Метод ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: f3b29b3ceda521afe9543588af332531aa03e84e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697419"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="c3bda-102">Метод ICorDebugExceptionDebugEvent::GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="c3bda-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>

<span data-ttu-id="c3bda-103">Получает собственный указатель инструкции для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="c3bda-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3bda-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3bda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3bda-105">Parameters</span></span>  

 `pIP`  
 <span data-ttu-id="c3bda-106">[out] Указатель на указатель инструкции для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="c3bda-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="c3bda-107">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="c3bda-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3bda-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c3bda-108">Remarks</span></span>  

 <span data-ttu-id="c3bda-109">Смысл этого указателя инструкции стека зависит от типа события, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c3bda-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c3bda-110">Тип события</span><span class="sxs-lookup"><span data-stu-id="c3bda-110">Event type</span></span>|<span data-ttu-id="c3bda-111">Смысл значения `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="c3bda-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="c3bda-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="c3bda-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="c3bda-113">Адрес инструкции со сбоем.</span><span class="sxs-lookup"><span data-stu-id="c3bda-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="c3bda-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="c3bda-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="c3bda-115">Адрес кода в кадре, указанный методом [жетстаккпоинтер](icordebugexceptiondebugevent-getstackpointer-method.md) , где выполнение возобновится, если исключение не было вызвано.</span><span class="sxs-lookup"><span data-stu-id="c3bda-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="c3bda-116">Исключение может вызывать или не вызывать другой код, например блок catch предложения `try/catch/finally`, выполняемый в этом фрейме.</span><span class="sxs-lookup"><span data-stu-id="c3bda-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="c3bda-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="c3bda-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="c3bda-118">Адрес кода, с которого начнется `catch` выполнение обработчика в кадре, указанном методом [жетстаккпоинтер](icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c3bda-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="c3bda-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="c3bda-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="c3bda-120">`pIP` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="c3bda-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="c3bda-121">Тип события доступен в методе [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c3bda-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3bda-122">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c3bda-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bda-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c3bda-123">Requirements</span></span>  

 <span data-ttu-id="c3bda-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3bda-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bda-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3bda-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3bda-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3bda-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3bda-127">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bda-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bda-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c3bda-128">See also</span></span>

- [<span data-ttu-id="c3bda-129">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c3bda-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="c3bda-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c3bda-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
