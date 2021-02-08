---
description: 'Дополнительные сведения: структура COR_GC_THREAD_STATS'
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
ms.openlocfilehash: 179eb335e9f8c118ee98d4b777c347f3758ee0c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799789"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`PerThreadAllocation`|Число байтов памяти, выделенных в потоке, связанном с текущим `COR_GC_THREAD_STATS` экземпляром. Это число сбрасывается в ноль каждый раз, когда происходит сборка мусора нулевого поколения.|  
|`Flags`|Число байтов, преобразованных в более высокое поколение при последней сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 [ICLRTask:: жетмемстатс](iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](hosting-structures.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
