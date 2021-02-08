---
description: 'Дополнительные сведения: структура COR_GC_REFERENCE'
title: Структура COR_GC_REFERENCE
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
ms.openlocfilehash: 38518bb1eb870081621bf32af9e63cdaa208dbd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801817"
---
# <a name="cor_gc_reference-structure"></a>Структура COR_GC_REFERENCE

Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`domain`|Указатель на домен приложения, которому принадлежит маркер или объект. Его значение может быть `null` .|  
|`location`|Интерфейс ICorDebugValue или ICorDebugReferenceValue, соответствующий объекту, который должен быть собран сборщиком мусора.|  
|`type`|Значение перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) , указывающее, откуда поступил корень. Дополнительные сведения см. в разделе «Примечания».|  
|`extraData`|Дополнительные данные об объекте, который должен быть собран сборщиком мусора. Эти сведения зависят от источника объекта, как указано в `type` поле. Дополнительные сведения см. в разделе «Примечания».|  
  
## <a name="remarks"></a>Remarks  

 `type`Поле является значением перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) , которое указывает, откуда поступила ссылка. Конкретное `COR_GC_REFERENCE` значение может отражать любой из следующих видов управляемых объектов:  
  
- Объекты из всех управляемых стеков ( `CorGCReferenceType.CorReferenceStack` ). Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.  
  
- Объекты из таблицы Handle ( `CorGCReferenceType.CorHandle*` ). Это включает в себя строгие ссылки ( `HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT` ) и статические переменные в модуле.  
  
- Объекты из очереди метода завершения ( `CorGCReferenceType.CorReferenceFinalizer` ). Очередь метода завершения помещает объекты в корни до запуска метода завершения.  
  
 `extraData`Поле содержит дополнительные данные в зависимости от источника (или типа) ссылки. Доступны следующие значения:  
  
- `DependentSource`. Если `type` имеет значение `CorGCREferenceType.CorHandleStrongDependent` , то это поле является объектом, в котором в случае со сроком существования объект, который должен быть собран в мусор, находится в корне `COR_GC_REFERENCE.Location` .  
  
- `RefCount`. Если значение `type` равно `CorGCREferenceType.CorHandleStrongRefCount` , это поле представляет собой счетчик ссылок для маркера.  
  
- `Size`. Если значение `type` равно `CorGCREferenceType.CorHandleStrongSizedByref` , это поле является последним размером дерева объектов, для которого сборщик мусора вычисляет корни объекта. Обратите внимание, что это вычисление не обязательно в актуальном состоянии.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
