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
ms.openlocfilehash: b7a068efcf20b2028e9c193567d15b59e582febf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500927"
---
# <a name="cor_prf_gc_generation-enumeration"></a>Перечисление COR_PRF_GC_GENERATION
Определяет создание коллекции мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|Объект сохраняется как поколение 0.|  
|`COR_PRF_GC_GEN_1`|Объект сохраняется как поколение 1.|  
|`COR_PRF_GC_GEN_2`|Объект сохраняется как поколение 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Объект хранится в куче больших объектов.|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|Объект хранится в куче закрепленных объектов.|  
  
## <a name="remarks"></a>Примечания  
 Сборщик мусора повышает производительность управления памятью, разделив объекты на поколения на основе возраста. В настоящее время сборщик мусора использует три поколения, нумерованный 0, 1 и 2, а также два специальных сегмента кучи: один для больших объектов и один для закрепленных объектов.
  
 Объекты, размер которых превышает пороговое значение, хранятся в куче больших объектов. Закрепленные объекты можно выделить в куче закрепленных объектов, чтобы избежать затрат на производительность при их выделении в обычных кучах. Другие выделенные объекты начинают принадлежать к поколению 0. Все объекты, существующие после сборки мусора в поколении 0, переходят в поколение 1. Объекты, существующие после сборки мусора в поколении 1, переходят в поколение 2.  
  
 Использование поколений означает, что сборщик мусора должен работать только с подмножеством выделенных объектов в один момент времени.  
  
 `COR_PRF_GC_GENERATION`Перечисление используется структурой [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](profiling-enumerations.md)
