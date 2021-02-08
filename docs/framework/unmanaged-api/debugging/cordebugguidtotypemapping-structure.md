---
description: 'Дополнительные сведения о: структура Кордебуггуидтотипемаппинг'
title: Структура CorDebugGuidToTypeMapping
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
ms.openlocfilehash: 5f6e99a17483b4fc16eb36ebb5fb5fd81380944b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801622"
---
# <a name="cordebugguidtotypemapping-structure"></a>Структура CorDebugGuidToTypeMapping

Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`iid`|Идентификатор GUID кэшированного типа среда выполнения Windows.|  
|`pType`|Указатель на объект ICorDebugType, предоставляющий сведения о кэшированном типе.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** среда выполнения Windows.  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
