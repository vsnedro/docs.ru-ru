---
title: Структура COR_GC_THREAD_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 88e81779fc9c20c506f3b0aa11ac2da3958dfe86
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616701"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="091fd-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="091fd-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="091fd-103">Содержит статистику по каждому потоку, относящуюся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="091fd-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="091fd-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="091fd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="091fd-105">Members</span></span>  
  
|<span data-ttu-id="091fd-106">Член</span><span class="sxs-lookup"><span data-stu-id="091fd-106">Member</span></span>|<span data-ttu-id="091fd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="091fd-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="091fd-108">Число байтов памяти, выделенных в потоке, связанном с текущим `COR_GC_THREAD_STATS` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="091fd-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="091fd-109">Это число сбрасывается в ноль каждый раз, когда происходит сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="091fd-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="091fd-110">Число байтов, преобразованных в более высокое поколение при последней сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="091fd-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="091fd-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="091fd-111">Remarks</span></span>  
 <span data-ttu-id="091fd-112">[ICLRTask:: жетмемстатс](iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="091fd-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091fd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="091fd-113">Requirements</span></span>  
 <span data-ttu-id="091fd-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="091fd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091fd-115">**Заголовок:** Гчост. idl</span><span class="sxs-lookup"><span data-stu-id="091fd-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="091fd-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="091fd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="091fd-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="091fd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091fd-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="091fd-118">See also</span></span>

- [<span data-ttu-id="091fd-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="091fd-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="091fd-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="091fd-120">IHostTask Interface</span></span>](ihosttask-interface.md)
