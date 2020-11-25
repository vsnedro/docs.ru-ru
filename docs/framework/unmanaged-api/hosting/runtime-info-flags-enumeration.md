---
title: Перечисление RUNTIME_INFO_FLAGS
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 6f4fbb40053628d60ba7f094fcb5d50a94d63e1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729945"
---
# <a name="runtime_info_flags-enumeration"></a>Перечисление RUNTIME_INFO_FLAGS

Содержит значения, которые указывают, какие сведения о среде CLR должны быть возвращены.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Указывает, что сведения о каталоге не следует включать.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Указывает, что сведения о версии указывать не следует.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Указывает, что при сбое не должно отображаться диалоговое окно ошибки.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Указывает, что эффекты вызова функции [функцию SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) с флагом SEM_FAILCRITICALERRORS должны быть переопределены. То есть диалоговое окно установки должно отображаться при сбое, а не подавлено.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Указывает запрос сведений о версии среды выполнения, совместимой с AMD-64.|  
|`RUNTIME_INFO_REQUEST_IA64`|Указывает запрос сведений о версии среды выполнения, совместимой с IA-64.|  
|`RUNTIME_INFO_REQUEST_X86`|Указывает запрос сведений о версии среды выполнения, совместимой с x86.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Указывает, что должны быть добавлены сведения об обновлении версии.|  
  
## <a name="remarks"></a>Комментарии  

 Следующие флаги архитектуры платформы могут быть указаны только один за раз и не могут быть объединены:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение перечислений](hosting-enumerations.md)
