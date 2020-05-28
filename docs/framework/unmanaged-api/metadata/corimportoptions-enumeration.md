---
title: Перечисление CorImportOptions
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 3be8a004be752af8a8675a3499bdb6cbfd785840
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009201"
---
# <a name="corimportoptions-enumeration"></a>Перечисление CorImportOptions
Содержит значения флага, управляющие поведением во время импорта сборки за пределы текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDImportOptionDefault`|Указывает поведение по умолчанию, которое пропускает удаленные записи.|  
|`MDImportOptionAll`|Указывает, что необходимо перечислить все метаданные.|  
|`MDImportOptionAllTypeDefs`|Указывает, что необходимо перечислить все определения типов, включая удаленные.|  
|`MDImportOptionAllMethodDefs`|Указывает, что необходимо перечислить все Месоддефс, включая удаленные.|  
|`MDImportOptionAllFieldDefs`|Указывает, что необходимо перечислить все Фиелддефс, включая удаленные.|  
|`MDImportOptionAllProperties`|Указывает, что необходимо перечислить все Пропертидефс, включая удаленные.|  
|`MDImportOptionAllEvents`|Указывает, что необходимо перечислить все Евентдефс, включая удаленные.|  
|`MDImportOptionAllCustomAttributes`|Указывает, что необходимо перечислить все настраиваемые атрибуты, включая удаленные.|  
|`MDImportOptionAllExportedTypes`|Указывает, что должны быть перечислены все экспортированные типы, включая удаленные.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
