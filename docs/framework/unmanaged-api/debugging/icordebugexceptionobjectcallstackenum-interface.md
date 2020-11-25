---
title: Интерфейс ICorDebugExceptionObjectCallStackEnum
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 1c45faecdb8b95af8d9e981962151c2c5d071a4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731895"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="8cf33-102">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="8cf33-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="8cf33-103">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="8cf33-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="8cf33-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="8cf33-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cf33-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8cf33-105">Methods</span></span>  
  
|<span data-ttu-id="8cf33-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8cf33-106">Method</span></span>|<span data-ttu-id="8cf33-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8cf33-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cf33-108">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="8cf33-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="8cf33-109">Возвращает указанное число объектов [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) , содержащих сведения о стеке вызовов объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="8cf33-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cf33-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8cf33-110">Remarks</span></span>  

 <span data-ttu-id="8cf33-111">`ICorDebugExceptionObjectCallStackEnum`Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="8cf33-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="8cf33-112">`ICorDebugExceptionObjectCallStackEnum`Экземпляр заполняется объектами [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) путем вызова метода [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8cf33-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="8cf33-113">Элементы стека вызовов в коллекции можно перечислить, вызвав метод [ICorDebugExceptionObjectCallStackEnum:: Next.](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="8cf33-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf33-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8cf33-114">Requirements</span></span>  

 <span data-ttu-id="8cf33-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cf33-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf33-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cf33-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cf33-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cf33-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cf33-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf33-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf33-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8cf33-119">See also</span></span>

- [<span data-ttu-id="8cf33-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8cf33-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8cf33-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="8cf33-121">Debugging</span></span>](index.md)
