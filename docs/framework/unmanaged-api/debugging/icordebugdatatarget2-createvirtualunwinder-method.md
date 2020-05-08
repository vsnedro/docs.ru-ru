---
title: Метод ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 7a479fba9bbcf28c60474fffc6219af23e62c251
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976503"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="1dc16-102">Метод ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="1dc16-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="1dc16-103">Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).</span><span class="sxs-lookup"><span data-stu-id="1dc16-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1dc16-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dc16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1dc16-105">Parameters</span></span>  
 <span data-ttu-id="1dc16-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="1dc16-106">nativeThreadID</span></span>  
 <span data-ttu-id="1dc16-107">[входной] Идентификатор собственного потока, стек которого должен быть очищен.</span><span class="sxs-lookup"><span data-stu-id="1dc16-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="1dc16-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="1dc16-108">contextFlags</span></span>  
 <span data-ttu-id="1dc16-109">[входной] Флаги, указывающие, какие части контекста определены в `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="1dc16-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="1dc16-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="1dc16-110">cbContext</span></span>  
 <span data-ttu-id="1dc16-111">[входной] Размер `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="1dc16-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="1dc16-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="1dc16-112">initialContext</span></span>  
 <span data-ttu-id="1dc16-113">[входной] Данные в контексте.</span><span class="sxs-lookup"><span data-stu-id="1dc16-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="1dc16-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="1dc16-114">ppUnwinder</span></span>  
 <span data-ttu-id="1dc16-115">[выходной] Указатель на адрес объекта интерфейса ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="1dc16-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dc16-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1dc16-116">Return Value</span></span>  
 <span data-ttu-id="1dc16-117">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="1dc16-117">`S_OK` if successful.</span></span> <span data-ttu-id="1dc16-118">Любое другое значение `HRESULT` указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="1dc16-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="1dc16-119">Любой сбой, `HRESULT` полученный mscordbi, считается неустранимым [ICorDebug](icordebug-interface.md) и приводит к возврату `CORDBG_E_DATA_TARGET_ERROR`методов ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="1dc16-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dc16-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="1dc16-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1dc16-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="1dc16-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dc16-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1dc16-122">Requirements</span></span>  
 <span data-ttu-id="1dc16-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dc16-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dc16-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1dc16-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dc16-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dc16-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dc16-126">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dc16-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dc16-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1dc16-127">See also</span></span>

- [<span data-ttu-id="1dc16-128">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="1dc16-128">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="1dc16-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1dc16-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
