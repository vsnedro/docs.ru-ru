---
title: Перечисление VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725265"
---
# <a name="variablelocationtype-enumeration"></a>Перечисление VariableLocationType

Указывает тип собственного расположения переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`VLT_REGISTER`|Переменная находится в регистре.|  
|`VLT_REGISTER_RELATIVE`|Переменная находится в расположении в памяти относительно регистра.|  
|`VLT_INVALID`|Переменная не хранится в регистре или расположении в памяти относительно регистра.|  
  
## <a name="remarks"></a>Комментарии  

 Член `VariableLocationType` перечисления возвращается методом [ICorDebugVariableHome:: жетлокатионтипе](icordebugvariablehome-getlocationtype-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления отладки](debugging-enumerations.md)
