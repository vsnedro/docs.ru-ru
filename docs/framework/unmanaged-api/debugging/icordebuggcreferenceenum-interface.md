---
title: Интерфейс ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 12ce800cb83ef4f79710aa441b50be860526023c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728125"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="b6882-102">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b6882-102">ICorDebugGCReferenceEnum Interface</span></span>

<span data-ttu-id="b6882-103">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="b6882-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6882-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b6882-104">Methods</span></span>  
  
|<span data-ttu-id="b6882-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b6882-105">Method</span></span>|<span data-ttu-id="b6882-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6882-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6882-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="b6882-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="b6882-108">Возвращает указанное число экземпляров [COR_GC_REFERENCE](cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="b6882-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6882-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b6882-109">Remarks</span></span>  

 <span data-ttu-id="b6882-110">`ICorDebugGCReferenceEnum`Интерфейс реализует интерфейс "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="b6882-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="b6882-111">`ICorDebugGCReferenceEnum`Экземпляр заполняется [COR_GC_REFERENCE](cor-gc-reference-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератегкреференцес](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b6882-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="b6882-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) объекты можно перечислить, вызвав метод [Икордебуггкреференце:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b6882-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="b6882-113">[COR_GC_REFERENCE](cor-gc-reference-structure.md) объекты в коллекции, заполненной этим методом, представляют три вида объектов:</span><span class="sxs-lookup"><span data-stu-id="b6882-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="b6882-114">Объекты из всех управляемых стеков.</span><span class="sxs-lookup"><span data-stu-id="b6882-114">Objects from all managed stacks.</span></span> <span data-ttu-id="b6882-115">Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b6882-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="b6882-116">Объекты из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="b6882-116">Objects from the handle table.</span></span> <span data-ttu-id="b6882-117">Это включает в себя строгие ссылки ( `HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT` ) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="b6882-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="b6882-118">Объекты из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="b6882-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="b6882-119">Очередь метода завершения помещает объекты в корни до запуска метода завершения.</span><span class="sxs-lookup"><span data-stu-id="b6882-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6882-120">Требования</span><span class="sxs-lookup"><span data-stu-id="b6882-120">Requirements</span></span>  

 <span data-ttu-id="b6882-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6882-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6882-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6882-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6882-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6882-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6882-124">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6882-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6882-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b6882-125">See also</span></span>

- [<span data-ttu-id="b6882-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b6882-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
