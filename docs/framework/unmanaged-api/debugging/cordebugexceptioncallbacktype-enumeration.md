---
description: Дополнительные сведения о перечислении CorDebugExceptionCallbackType
title: Перечисление CorDebugExceptionCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
ms.openlocfilehash: 41b9cdf707de017703ee3756b3d04a38163bb03b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801687"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a>Перечисление CorDebugExceptionCallbackType

Указывает тип обратного вызова, сделанный из события [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|Возникло исключение.|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|Процесс, виндуп исключение, вошел в пользовательский код.|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|Процесс виндуп исключения обнаружил `catch` блок в пользовательском коде.|  
|`DEBUG_EXCEPTION_UNHANDLED`|Исключение не было обработано.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
