---
description: 'Дополнительные сведения: перечисление COR_GC_STAT_TYPES'
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
ms.openlocfilehash: c4ea3175c777d49a5d6cffdf506f42e479784971
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799813"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структура COR_GC_STATS](cor-gc-stats-structure.md)
- [Размещение перечислений](hosting-enumerations.md)
