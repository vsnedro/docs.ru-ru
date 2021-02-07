---
description: 'Дополнительные сведения: структура COR_SEGMENT'
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
ms.openlocfilehash: 9bbc452b2c2036d019175ac1be8b9917ffa07b6a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712198"
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
  
## <a name="remarks"></a>Remarks  

 Структура `COR_SEGMENTS` представляет область памяти в управляемой куче.  Объекты `COR_SEGMENTS` являются членами объекта коллекции [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), которая заполняется путем вызова метода [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md).  
  
 В поле `heap` указан номер обработчика, который соответствует определенной куче. Для сборщиков мусора на рабочей станции это значение всегда равно нулю, ведь на рабочих станциях только одна куча сборки мусора. Для сборщиков мусора на сервере это значение соответствует обработчику, к которому привязана куча. Куч сборки мусора может быть больше или меньше фактического числа обработчиков в связи с особенностями реализации сборщика мусора.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
