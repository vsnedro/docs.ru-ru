---
title: Перечисление COR_GC_STAT_TYPES
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: d7e78dfc4beba67cc376b221d0cd49f7200f5d23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501707"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="8c7bf-102">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="8c7bf-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="8c7bf-103">Указывает статистику, записываемую для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8c7bf-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c7bf-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="8c7bf-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c7bf-105">Remarks</span></span>  
 <span data-ttu-id="8c7bf-106">Это перечисление указывает, какая статистика в структуре [COR_GC_STATS](cor-gc-stats-structure.md) должна быть задана методом [Иклргкманажер:: stats](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c7bf-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="8c7bf-107">Участники</span><span class="sxs-lookup"><span data-stu-id="8c7bf-107">Members</span></span>  
  
|<span data-ttu-id="8c7bf-108">Член</span><span class="sxs-lookup"><span data-stu-id="8c7bf-108">Member</span></span>|<span data-ttu-id="8c7bf-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8c7bf-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="8c7bf-110">Записывает количество сборок мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="8c7bf-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="8c7bf-111">Записывает статистику использования памяти и размера сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8c7bf-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c7bf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8c7bf-112">Requirements</span></span>  
 <span data-ttu-id="8c7bf-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c7bf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c7bf-114">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="8c7bf-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8c7bf-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c7bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7bf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8c7bf-116">See also</span></span>

- [<span data-ttu-id="8c7bf-117">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="8c7bf-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="8c7bf-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="8c7bf-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
