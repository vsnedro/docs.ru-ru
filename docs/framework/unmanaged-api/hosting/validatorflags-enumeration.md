---
title: Перечисление ValidatorFlags
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: d5eb225241f597baf7a0a5584f4aaf8bf8411ea2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009474"
---
# <a name="validatorflags-enumeration"></a>Перечисление ValidatorFlags
Содержит значения, указывающие тип проверки, которая должна быть выполнена при вызове метода [иклрвалидатор:: Validate](iclrvalidator-validate-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Указывает, что следует проверять только промежуточный язык MSIL в исполняемом файле.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Указывает, что должен проверяться только формат исполняемого файла.|  
|`VALIDATOR_EXTRA_VERBOSE`|Указывает, что следует выполнять все типы проверки и сообщать о них.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Указывает, что формат исполняемого файла не должен проверяться.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Указывает, что сообщения об ошибках проверки должны включать строки исходного кода, вызывающие ошибки проверки. Это значение поля недопустимо в .NET Framework версии 2,0.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
