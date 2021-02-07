---
description: 'Дополнительные сведения: структура COR_FIELD'
title: Структура COR_FIELD
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
ms.openlocfilehash: a3e9dcc2a5c3bb2abae42dab4292c1d285df5ad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747116"
---
# <a name="cor_field-structure"></a>Структура COR_FIELD

Предоставляет сведения о поле в объекте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`token`|`mdFieldDef`Токен, который можно использовать для получения сведений о полях.|  
|`offset`|Смещение в байтах для данных поля в объекте.|  
|`id`|Значение [COR_TYPEID](cor-typeid-structure.md) , определяющее тип этого поля.|  
|`fieldType`|Значение перечисления Корелементтипе, указывающее тип поля.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
