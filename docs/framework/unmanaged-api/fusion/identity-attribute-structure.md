---
description: 'Дополнительные сведения: структура IDENTITY_ATTRIBUTE'
title: Структура IDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
ms.openlocfilehash: 52610961ab202fc79351073eac1846a1a63889e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800179"
---
# <a name="identity_attribute-structure"></a>Структура IDENTITY_ATTRIBUTE

Содержит сведения об атрибутах метаданных для экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`pszNamespace`|Указатель на строку символов, завершающуюся нулем, которая содержит пространство имен, в котором находится атрибут.|  
|`pszName`|Указатель на строку символов, завершающуюся нулем, которая содержит имя атрибута.|  
|`pszValue`|Указатель на строку символов, завершающуюся нулем, которая содержит значение атрибута.|  
  
## <a name="remarks"></a>Remarks  

 `IDENTITY_ATTRIBUTE`Структура содержит три указателя на строки символов, заканчивающиеся нулем. Эти три строки описывают один атрибут.  
  
 Экземпляр `IDENTITY_ATTRIBUTE` структуры связан с экземпляром структуры [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . `IDENTITY_ATTRIBUTE`Структура содержит фактические строки, а соответствующая `IDENTITY_ATTRIBUTE_BLOB` Структура перечисляет смещения для трех строк, перечисленных в `IDENTITY_ATTRIBUTE` структуре.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IDefinitionIdentity](idefinitionidentity-interface.md)
- [Структура IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)
- [Структуры Fusion](fusion-structures.md)
