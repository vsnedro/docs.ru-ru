---
title: Перечисление CorRegFlags
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: 5ea588194720394ad9f361fbba702f3fcdcbe110
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706103"
---
# <a name="corregflags-enumeration"></a>Перечисление CorRegFlags

Предоставляет значения флагов, используемые для регистрации при установке модуля или составного образа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`regNoCopy`|Указывает, что файлы не должны копироваться в место назначения.|  
|`regConfig`|Указывает, что модуль или составной является конфигурацией.|  
|`regHasRefs`|Указывает, что модуль или составная ссылка содержит ссылки на классы.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
