---
title: Перечисление COR_PRF_GC_GENERATION
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: 1d7489e997868a9486f77d176580cee18213a99d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718568"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="70e18-102">Перечисление COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="70e18-102">COR_PRF_GC_GENERATION Enumeration</span></span>

<span data-ttu-id="70e18-103">Определяет создание коллекции мусора.</span><span class="sxs-lookup"><span data-stu-id="70e18-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70e18-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="70e18-105">Члены</span><span class="sxs-lookup"><span data-stu-id="70e18-105">Members</span></span>  
  
|<span data-ttu-id="70e18-106">Член</span><span class="sxs-lookup"><span data-stu-id="70e18-106">Member</span></span>|<span data-ttu-id="70e18-107">Описание</span><span class="sxs-lookup"><span data-stu-id="70e18-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="70e18-108">Объект сохраняется как поколение 0.</span><span class="sxs-lookup"><span data-stu-id="70e18-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="70e18-109">Объект сохраняется как поколение 1.</span><span class="sxs-lookup"><span data-stu-id="70e18-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="70e18-110">Объект сохраняется как поколение 2.</span><span class="sxs-lookup"><span data-stu-id="70e18-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="70e18-111">Объект хранится в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="70e18-111">The object is stored in the large-object heap.</span></span>|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|<span data-ttu-id="70e18-112">Объект хранится в куче закрепленных объектов.</span><span class="sxs-lookup"><span data-stu-id="70e18-112">The object is stored in the pinned-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70e18-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="70e18-113">Remarks</span></span>  

 <span data-ttu-id="70e18-114">Сборщик мусора повышает производительность управления памятью, разделив объекты на поколения на основе возраста.</span><span class="sxs-lookup"><span data-stu-id="70e18-114">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="70e18-115">В настоящее время сборщик мусора использует три поколения, нумерованный 0, 1 и 2, а также два специальных сегмента кучи: один для больших объектов и один для закрепленных объектов.</span><span class="sxs-lookup"><span data-stu-id="70e18-115">The garbage collector currently uses three generations, numbered 0, 1, and 2, and two special heap segments, one for large objects and one for pinned objects.</span></span>
  
 <span data-ttu-id="70e18-116">Объекты, размер которых превышает пороговое значение, хранятся в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="70e18-116">Objects whose size is larger than a threshold value are stored in the large-object heap.</span></span> <span data-ttu-id="70e18-117">Закрепленные объекты можно выделить в куче закрепленных объектов, чтобы избежать затрат на производительность при их выделении в обычных кучах.</span><span class="sxs-lookup"><span data-stu-id="70e18-117">Pinned objects can be allocated to the pinned-object heap to avoid the performance cost of allocating them on the normal heaps.</span></span> <span data-ttu-id="70e18-118">Другие выделенные объекты начинают принадлежать к поколению 0.</span><span class="sxs-lookup"><span data-stu-id="70e18-118">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="70e18-119">Все объекты, существующие после сборки мусора в поколении 0, переходят в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="70e18-119">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="70e18-120">Объекты, существующие после сборки мусора в поколении 1, переходят в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="70e18-120">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="70e18-121">Использование поколений означает, что сборщик мусора должен работать только с подмножеством выделенных объектов в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="70e18-121">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="70e18-122">`COR_PRF_GC_GENERATION`Перечисление используется структурой [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="70e18-122">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70e18-123">Требования</span><span class="sxs-lookup"><span data-stu-id="70e18-123">Requirements</span></span>  

 <span data-ttu-id="70e18-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70e18-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70e18-125">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70e18-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70e18-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70e18-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70e18-127">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70e18-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e18-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="70e18-128">See also</span></span>

- [<span data-ttu-id="70e18-129">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="70e18-129">Profiling Enumerations</span></span>](profiling-enumerations.md)
