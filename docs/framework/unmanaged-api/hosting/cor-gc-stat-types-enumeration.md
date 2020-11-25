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
ms.openlocfilehash: c14e27b67fc600e2684f8c967af30bb9a5cee126
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716747"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="55fb8-102">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="55fb8-102">COR_GC_STAT_TYPES Enumeration</span></span>

<span data-ttu-id="55fb8-103">Указывает статистику, записываемую для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="55fb8-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55fb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55fb8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="55fb8-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="55fb8-105">Remarks</span></span>  

 <span data-ttu-id="55fb8-106">Это перечисление указывает, какая статистика в структуре [COR_GC_STATS](cor-gc-stats-structure.md) должна быть задана методом [Иклргкманажер:: stats](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="55fb8-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="55fb8-107">Элементы</span><span class="sxs-lookup"><span data-stu-id="55fb8-107">Members</span></span>  
  
|<span data-ttu-id="55fb8-108">Член</span><span class="sxs-lookup"><span data-stu-id="55fb8-108">Member</span></span>|<span data-ttu-id="55fb8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="55fb8-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="55fb8-110">Записывает количество сборок мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="55fb8-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="55fb8-111">Записывает статистику использования памяти и размера сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="55fb8-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55fb8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="55fb8-112">Requirements</span></span>  

 <span data-ttu-id="55fb8-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55fb8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55fb8-114">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="55fb8-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="55fb8-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55fb8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55fb8-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55fb8-116">See also</span></span>

- [<span data-ttu-id="55fb8-117">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="55fb8-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="55fb8-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="55fb8-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
