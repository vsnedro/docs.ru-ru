---
description: Дополнительные сведения о перечислении CorDebugInternalFrameType
title: Перечисление CorDebugInternalFrameType
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
ms.openlocfilehash: 0479ae7602224e03086b9dacf91d360253b61818
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662004"
---
# <a name="cordebuginternalframetype-enumeration"></a>Перечисление CorDebugInternalFrameType

Указывает тип кадра стека. Это перечисление используется методом [ICorDebugInternalFrame:: GetFrameType](icordebuginternalframe-getframetype-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Значение Null. `ICorDebugInternalFrame::GetFrameType`Метод никогда не возвращает это значение.|  
|`STUBFRAME_M2U`|Фрейм заглушки "управляемый-к-неуправляемый".|  
|`STUBFRAME_U2M`|Неуправляемый фрейм заглушки.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Переход между доменами приложений.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Вызов упрощенного метода.|  
|`STUBFRAME_FUNC_EVAL`|Начало вычисления функции.|  
|`STUBFRAME_INTERNALCALL`|Внутренний вызов среды CLR.|  
|`STUBFRAME_CLASS_INIT`|Начало инициализации класса.|  
|`STUBFRAME_EXCEPTION`|Порождается исключение.|  
|`STUBFRAME_SECURITY`|Кадр, используемый для управления доступом для кода.|  
|`STUBFRAME_JIT_COMPILATION`|Среда выполнения — это JIT-компиляция метода.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
