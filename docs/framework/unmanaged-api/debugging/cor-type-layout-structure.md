---
title: Структура COR_TYPE_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: f33c8f5cf218979404063342d9b1cc5123839f83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726331"
---
# <a name="cor_type_layout-structure"></a>Структура COR_TYPE_LAYOUT

Предоставляет сведения о расположении объекта в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`parentID`|Идентификатор родительского типа для этого типа. Это будет идентификатор типа NULL (токен1 = 0, токен2 = 0), если идентификатор типа соответствует <xref:System.Object?displayProperty=nameWithType> .|  
|`objectSize`|Базовый размер объекта этого типа. Это общий размер для объектов, не имеющих переменного размера.|  
|`numFields`|Число полей, включаемых в объекты этого типа.|  
|`boxOffset`|Если этот тип упакован, начальное смещение полей объекта. Это поле допустимо только для типов значений, таких как примитивы и структуры.|  
|`type`|Корелементтипе, к которому принадлежит этот тип.|  
  
## <a name="remarks"></a>Комментарии  

 Если `numFields` значение больше нуля, можно вызвать метод [метод ICorDebugProcess5:: жеттипефиелдс](icordebugprocess5-gettypefields-method.md) для получения сведений о полях этого типа. Если `type` имеет значение `ELEMENT_TYPE_STRING` , `ELEMENT_TYPE_ARRAY` или `ELEMENT_TYPE_SZARRAY` , то размер объектов этого типа является переменным, и можно передать структуру [COR_TYPEID](cor-typeid-structure.md) в метод [метод ICorDebugProcess5:: жетаррайлайаут](icordebugprocess5-getarraylayout-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
