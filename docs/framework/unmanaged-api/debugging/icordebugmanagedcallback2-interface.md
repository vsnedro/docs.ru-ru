---
title: Интерфейс ICorDebugManagedCallback2
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: 937a2fb322eb63461d90e215635e1b10ab6afd09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689788"
---
# <a name="icordebugmanagedcallback2-interface"></a>Интерфейс ICorDebugManagedCallback2

Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). `ICorDebugManagedCallback2` является логическим расширением интерфейса [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md)|Уведомляет отладчик о том, что набор задач, связанных с указанным соединением, изменился.|  
|[Метод CreateConnection](icordebugmanagedcallback2-createconnection-method.md)|Уведомляет отладчик о создании нового соединения.|  
|[Метод DestroyConnection](icordebugmanagedcallback2-destroyconnection-method.md)|Уведомляет отладчик о завершении указанного соединения.|  
|[Метод Exception](icordebugmanagedcallback2-exception-method.md)|Уведомляет отладчик о запуске поиска обработчика исключений.|  
|[Метод ExceptionUnwind](icordebugmanagedcallback2-exceptionunwind-method.md)|Предоставляет уведомление о состоянии во время процесса очистки исключения.|  
|[Метод FunctionRemapComplete](icordebugmanagedcallback2-functionremapcomplete-method.md)|Уведомляет отладчик о том, что выполнение кода переключено на новую версию измененной функции.|  
|[Метод FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md)|Уведомляет отладчик о том, что выполнение кода достигло точки последовательности в более ранней версии измененной функции.|  
|[Метод MDANotification](icordebugmanagedcallback2-mdanotification-method.md)|Предоставляет уведомление о том, что при выполнении кода было обнаружено сообщение MDA.|  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugManagedCallback2`Интерфейс расширяет `ICorDebugManagedCallback` интерфейс для поддержки новых событий отладки, появившихся в .NET Framework версии 2,0.  
  
 `ICorDebugManagedCallback2`При отладке приложений .NET Framework 2,0 в отладчике должен быть реализован. Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается как объект обратного вызова в [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
