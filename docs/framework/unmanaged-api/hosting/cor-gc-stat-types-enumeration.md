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
# <a name="cor_gc_stat_types-enumeration"></a>Перечисление COR_GC_STAT_TYPES

Указывает статистику, записываемую для сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Remarks  

 Это перечисление указывает, какая статистика в структуре [COR_GC_STATS](cor-gc-stats-structure.md) должна быть задана методом [Иклргкманажер:: stats](iclrgcmanager-getstats-method.md) .  
  
## <a name="members"></a>Элементы  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Записывает количество сборок мусора, выполненных для каждого поколения.|  
|`COR_GC_MEMORYUSAGE`|Записывает статистику использования памяти и размера сборки мусора.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структура COR_GC_STATS](cor-gc-stats-structure.md)
- [Размещение перечислений](hosting-enumerations.md)
