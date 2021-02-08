---
description: Дополнительные сведения о перечислении Кордебугилтонативемаппингтипес
title: Перечисление CorDebugIlToNativeMappingTypes
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: bcca11bf3c7574fe76684f6786d7408c80acfa43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801638"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a>Перечисление CorDebugIlToNativeMappingTypes

Указывает, соответствует ли определенный диапазон машинных инструкций, представленный экземпляром структуры COR_DEBUG_IL_TO_NATIVE_MAP, Специальному региону кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`NO_MAPPING`|Диапазон машинных инструкций не соответствует ни одной специальной области кода.|  
|`PROLOG`|Диапазон машинных инструкций соответствует прологу.|  
|`EPILOG`|Диапазон машинных инструкций соответствует заключительному фрагменту.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Перечисления отладки](debugging-enumerations.md)
