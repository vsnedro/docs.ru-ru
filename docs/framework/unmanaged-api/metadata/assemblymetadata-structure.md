---
title: Структура ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 8071c3f43775975de37e3255582b6fc8f13f7de3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732792"
---
# <a name="assemblymetadata-structure"></a>Структура ASSEMBLYMETADATA

Содержит сведения о сборке, на которую имеется ссылка, включая ее версию и уровень поддержки языковых стандартов, процессоров и операционных систем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`usMajorVersion`|Основной номер версии сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если заданы все биты `usMajorVersion` , основной номер версии не указывается.|  
|`usMinorVersion`|Дополнительный номер версии сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если заданы все биты `usMinorVersion` , дополнительный номер версии не указывается.|  
|`usBuildNumber`|Номер построения сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если заданы все биты `usBuildNumber` , номер сборки не указывается.|  
|`usRevisionNumber`|Номер редакции сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если заданы все биты `usRevisionNumber` , номер редакции не указывается.|  
|`szLocale`|Список имен языковых стандартов, которым соответствует спецификация RFC1766, разделенные точкой с запятой, с указанием языковых стандартов, поддерживаемых сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от языкового стандарта. **Примечание.**  В .NET Framework версии 1,0 нельзя указать более одного языкового стандарта.|  
|`cbLocale`|Размер в расширенных символах `szLocale` .|  
|`rdwProcessor`|Массив идентификаторов, как определено в Winnt. h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от процессора.|  
|`ulProcessor`|Длина массива `rdwProcessor`.|  
|`rOS`|Массив экземпляров [OSInfo](osinfo-structure.md) , указывающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от операционной системы.|  
|`ulOS`|Длина массива `rOS`.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры метаданных](metadata-structures.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Структура OSINFO](osinfo-structure.md)
