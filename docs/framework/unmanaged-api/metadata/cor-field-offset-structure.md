---
title: Структура COR_FIELD_OFFSET
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 1a8ab5aa5909af60089d5e4cc8092e15bc75e8cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724186"
---
# <a name="cor_field_offset-structure"></a>Структура COR_FIELD_OFFSET

Хранит смещение указанного поля в пределах класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`Токен метаданных, представляющий поле.|  
|`ulOffset`|Смещение поля в его классе.|  
  
## <a name="remarks"></a>Комментарии  

 Методы [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) и [IMetaDataEmit:: сеткласслайаут](imetadataemit-setclasslayout-method.md) принимают параметр типа `COR_FIELD_OFFSET` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h, CorProf. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры метаданных](metadata-structures.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
