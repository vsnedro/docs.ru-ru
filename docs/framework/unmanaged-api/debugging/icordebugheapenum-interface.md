---
title: Интерфейс ICorDebugHeapEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: ff290cd8ad331ff109c3bbbf87638d22b9b183bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208542"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="dbe00-102">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="dbe00-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="dbe00-103">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="dbe00-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="dbe00-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="dbe00-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbe00-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dbe00-105">Methods</span></span>  
  
|<span data-ttu-id="dbe00-106">Метод</span><span class="sxs-lookup"><span data-stu-id="dbe00-106">Method</span></span>|<span data-ttu-id="dbe00-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dbe00-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbe00-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="dbe00-108">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="dbe00-109">Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения об объектах в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="dbe00-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbe00-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbe00-110">Remarks</span></span>  
 <span data-ttu-id="dbe00-111">`ICorDebugHeapEnum`Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="dbe00-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="dbe00-112">`ICorDebugHeapEnum`Экземпляр заполняется [COR_HEAPOBJECT](cor-heapobject-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератехеап](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dbe00-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="dbe00-113">Каждый экземпляр [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции представляет собой либо динамический объект в куче, либо объект, который не является корневым для какого-либо объекта, но еще не был собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="dbe00-113">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="dbe00-114">Объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапенум:: Next](icordebugheapenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dbe00-114">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe00-115">Требования</span><span class="sxs-lookup"><span data-stu-id="dbe00-115">Requirements</span></span>  
 <span data-ttu-id="dbe00-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbe00-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe00-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbe00-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbe00-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe00-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe00-119">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe00-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe00-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dbe00-120">See also</span></span>

- [<span data-ttu-id="dbe00-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dbe00-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
