---
title: Структура COR_SEGMENT
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
ms.openlocfilehash: 738e29fa15340c76b055b608140f3c3bfbd29611
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726357"
---
# <a name="cor_segment-structure"></a>Структура COR_SEGMENT

Содержит сведения об области памяти в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;
    CORDB_ADDRESS end;
    CorDebugGenerationTypes gen;
    ULONG heap;
} COR_SEGMENT;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`start`|Начальный адрес области памяти.|  
|`end`|Конечный адрес области памяти.|  
|`gen`|Элемент перечисления [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md), который указывает на создание области памяти.|  
|`heap`|Номер кучи, в которой находится область памяти. Дополнительные сведения см. в разделе "Примечания".|  
  
## <a name="remarks"></a>Комментарии  

 Структура `COR_SEGMENTS` представляет область памяти в управляемой куче.  Объекты `COR_SEGMENTS` являются членами объекта коллекции [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), которая заполняется путем вызова метода [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md).  
  
 В поле `heap` указан номер обработчика, который соответствует определенной куче. Для сборщиков мусора на рабочей станции это значение всегда равно нулю, ведь на рабочих станциях только одна куча сборки мусора. Для сборщиков мусора на сервере это значение соответствует обработчику, к которому привязана куча. Куч сборки мусора может быть больше или меньше фактического числа обработчиков в связи с особенностями реализации сборщика мусора.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
