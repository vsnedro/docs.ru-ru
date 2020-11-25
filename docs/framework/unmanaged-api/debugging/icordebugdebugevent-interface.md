---
title: Интерфейс ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: d73857bd9d0d5dd9e5eff0c89dcc573ae0d93f0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731882"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="d7560-102">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d7560-102">ICorDebugDebugEvent Interface</span></span>

<span data-ttu-id="d7560-103">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="d7560-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7560-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d7560-104">Methods</span></span>  
  
|<span data-ttu-id="d7560-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d7560-105">Method</span></span>|<span data-ttu-id="d7560-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d7560-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7560-107">Метод GetEventKind</span><span class="sxs-lookup"><span data-stu-id="d7560-107">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="d7560-108">Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="d7560-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="d7560-109">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="d7560-109">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="d7560-110">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="d7560-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7560-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d7560-111">Remarks</span></span>  

 <span data-ttu-id="d7560-112">Следующие интерфейсы являются производными от интерфейса `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="d7560-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="d7560-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d7560-113">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="d7560-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d7560-114">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="d7560-115">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d7560-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="d7560-116">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d7560-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7560-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d7560-117">Requirements</span></span>  

 <span data-ttu-id="d7560-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7560-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7560-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7560-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7560-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7560-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7560-121">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7560-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7560-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d7560-122">See also</span></span>

- [<span data-ttu-id="d7560-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d7560-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d7560-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="d7560-124">Debugging</span></span>](index.md)
