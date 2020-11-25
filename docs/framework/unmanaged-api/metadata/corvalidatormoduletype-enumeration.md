---
title: Перечисление CorValidatorModuleType
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 2fb7f11677870f7d53439f1867f167fabe70b22a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723861"
---
# <a name="corvalidatormoduletype-enumeration"></a>Перечисление CorValidatorModuleType

Указывает тип модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|Недопустимый тип модуля.|  
|`ValidatorModuleTypeMin`|Минимальное значение `CorValidatorModuleType` перечисления.|  
|`ValidatorModuleTypePE`|Модуль является переносимым исполняемым файлом (PE).|  
|`ValidatorModuleTypeObj`|Модуль является OBJ-файлом.|  
|`ValidatorModuleTypeEnc`|Модуль является сеансом отладчика "изменить и продолжить".|  
|`ValidatorModuleTypeIncr`|Модуль — это один из инкрементно построенных.|  
|`ValidatorModuleTypeMax`|Максимальное значение `CorValidatorModuleType` перечисления.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
