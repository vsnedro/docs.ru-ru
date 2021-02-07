---
description: 'Дополнительные сведения о методе: ICorDebugProcess8:: Енабликсцептионкаллбакксаутсидеофмикоде'
title: Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: a85c9d62e5fb62fe620f0901509afa5a03504d4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691280"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode

[Поддерживается в платформа .NET Framework 4,6 и более поздних версиях]  
  
 Включает или отключает определенные типы обратных вызовов исключений [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Remarks  

 Если `enableExceptionsOutsideOfJMC` имеет значение `false`:  
  
- Исключение DEBUG_EXCEPTION_FIRST_CHANCE не будет приводить к обратному вызову отладчика.  
  
- Исключение DEBUG_EXCEPTION_CATCH_HANDLER_FOUND не приводит к обратному вызову отладчика, если исключение никогда не попадает в пользовательский код (то есть путь от источника исключения в обработчик исключений не имеет методов, помеченных как JustMyCode или JMC).  
  
 Значением свойства `enableExceptionsOutsideOfJMC` по умолчанию является `true`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
