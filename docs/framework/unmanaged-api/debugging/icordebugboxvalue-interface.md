---
title: Интерфейс ICorDebugBoxValue
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: 6d58ae048382a78c422703d5c6caeb3bbc739849
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723172"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="cc72f-102">Интерфейс ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="cc72f-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="cc72f-103">Подкласс "ICorDebugHeapValue", представляющий объект класса упакованного значения.</span><span class="sxs-lookup"><span data-stu-id="cc72f-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc72f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cc72f-104">Methods</span></span>  
  
|<span data-ttu-id="cc72f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cc72f-105">Method</span></span>|<span data-ttu-id="cc72f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cc72f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc72f-107">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="cc72f-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="cc72f-108">Возвращает указатель интерфейса на упакованный экземпляр "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="cc72f-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc72f-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cc72f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc72f-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cc72f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc72f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cc72f-111">Requirements</span></span>  

 <span data-ttu-id="cc72f-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc72f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc72f-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc72f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc72f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc72f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc72f-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc72f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc72f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc72f-116">See also</span></span>

- [<span data-ttu-id="cc72f-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cc72f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
