---
title: Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: e45b180ac6d943d89740ad7ae10500ea4ad1aa9c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975970"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="515b4-102">Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="515b4-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="515b4-103">Возвращает перечислитель для стека вызовов, внедренного в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="515b4-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="515b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="515b4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="515b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="515b4-105">Parameters</span></span>  
 <span data-ttu-id="515b4-106">ппкаллстаккенум</span><span class="sxs-lookup"><span data-stu-id="515b4-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="515b4-107">заполняет Указатель на адрес объекта интерфейса [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) , который является перечислителем трассировки стека для управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="515b4-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="515b4-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="515b4-108">Remarks</span></span>  
 <span data-ttu-id="515b4-109">Если сведения о стеке вызовов недоступны, метод возвращает `S_OK`значение, а [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) — допустимый перечислитель с длиной 0.</span><span class="sxs-lookup"><span data-stu-id="515b4-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="515b4-110">Если методу не удается получить сведения о трассировке стека, возвращается значение `E_FAIL` , а перечислитель не возвращается.</span><span class="sxs-lookup"><span data-stu-id="515b4-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="515b4-111">Объект [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) отвечает за декодирование данных трассировки стека из `_stackTrace` поля объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="515b4-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="515b4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="515b4-112">Requirements</span></span>  
 <span data-ttu-id="515b4-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="515b4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="515b4-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="515b4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="515b4-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="515b4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="515b4-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="515b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515b4-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="515b4-117">See also</span></span>

- [<span data-ttu-id="515b4-118">Интерфейс ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="515b4-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="515b4-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="515b4-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
