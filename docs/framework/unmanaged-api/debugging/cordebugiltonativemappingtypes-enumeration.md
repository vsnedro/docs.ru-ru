---
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
ms.openlocfilehash: 808fc70a308eff1b05aa49ea2bb89fe53377c973
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795850"
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
  
## <a name="members"></a>Участники  
  
|Участник|Описание|  
|------------|-----------------|  
|`NO_MAPPING`|Диапазон машинных инструкций не соответствует ни одной специальной области кода.|  
|`PROLOG`|Диапазон машинных инструкций соответствует прологу.|  
|`EPILOG`|Диапазон машинных инструкций соответствует заключительному фрагменту.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Перечисления отладки](debugging-enumerations.md)
