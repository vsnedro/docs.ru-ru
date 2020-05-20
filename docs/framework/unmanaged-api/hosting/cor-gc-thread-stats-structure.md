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
# <a name="cor_gc_thread_stats-structure"></a>Структура COR_GC_THREAD_STATS
Содержит статистику по каждому потоку, относящуюся к сборке мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`PerThreadAllocation`|Число байтов памяти, выделенных в потоке, связанном с текущим `COR_GC_THREAD_STATS` экземпляром. Это число сбрасывается в ноль каждый раз, когда происходит сборка мусора нулевого поколения.|  
|`Flags`|Число байтов, преобразованных в более высокое поколение при последней сборке мусора.|  
  
## <a name="remarks"></a>Комментарии  
 [ICLRTask:: жетмемстатс](iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Структуры размещения](hosting-structures.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
