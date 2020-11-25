---
title: Интерфейс ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695820"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="367ef-102">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="367ef-102">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="367ef-103">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="367ef-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="367ef-104">Методы</span><span class="sxs-lookup"><span data-stu-id="367ef-104">Methods</span></span>  
  
|<span data-ttu-id="367ef-105">Метод</span><span class="sxs-lookup"><span data-stu-id="367ef-105">Method</span></span>|<span data-ttu-id="367ef-106">Описание</span><span class="sxs-lookup"><span data-stu-id="367ef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="367ef-107">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="367ef-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="367ef-108">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="367ef-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="367ef-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="367ef-109">Remarks</span></span>  

 <span data-ttu-id="367ef-110">Типы событий [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) реализуют этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="367ef-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="367ef-111">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="367ef-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="367ef-112">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="367ef-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="367ef-113">Требования</span><span class="sxs-lookup"><span data-stu-id="367ef-113">Requirements</span></span>  

 <span data-ttu-id="367ef-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="367ef-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="367ef-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="367ef-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="367ef-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="367ef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="367ef-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="367ef-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367ef-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="367ef-118">See also</span></span>

- [<span data-ttu-id="367ef-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="367ef-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="367ef-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="367ef-120">Debugging</span></span>](index.md)
