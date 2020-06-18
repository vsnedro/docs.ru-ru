---
title: Интерфейс ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: acf490895db35af1c5d0d1e7fe7e3de5ae2a16b6
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904290"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="2cf60-102">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="2cf60-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="2cf60-103">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="2cf60-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="2cf60-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="2cf60-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cf60-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2cf60-105">Methods</span></span>  
  
|<span data-ttu-id="2cf60-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2cf60-106">Method</span></span>|<span data-ttu-id="2cf60-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2cf60-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cf60-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="2cf60-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="2cf60-109">Возвращает указанное число экземпляров [COR_SEGMENT](cor-segment-structure.md) , содержащих сведения о регионах управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="2cf60-109">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cf60-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cf60-110">Remarks</span></span>  
 <span data-ttu-id="2cf60-111">`ICorDebugHeapSegmentEnum`Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="2cf60-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="2cf60-112">`ICorDebugHeapSegmentEnum`Экземпляр заполняется [COR_SEGMENT](cor-segment-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератехеапрегионс](icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2cf60-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_SEGMENT](cor-segment-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="2cf60-113">Объекты [COR_SEGMENT](cor-segment-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапсегментенум:: Next](icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2cf60-113">The [COR_SEGMENT](cor-segment-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="2cf60-114">`ICorDebugHeapSegmentEnum`Объект Collection перечисляет все области памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах.</span><span class="sxs-lookup"><span data-stu-id="2cf60-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="2cf60-115">Он может включать сведения о пустых или зарезервированных регионах памяти.</span><span class="sxs-lookup"><span data-stu-id="2cf60-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf60-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2cf60-116">Requirements</span></span>  
 <span data-ttu-id="2cf60-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf60-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf60-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cf60-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cf60-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cf60-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cf60-120">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf60-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf60-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2cf60-121">See also</span></span>

- [<span data-ttu-id="2cf60-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2cf60-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
