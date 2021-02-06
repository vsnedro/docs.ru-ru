---
description: 'Дополнительные сведения о: интерфейс ICorDebugThread2'
title: Интерфейс ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: 81f687f6daff9ffa7298ec6d818a214b8934bcc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658507"
---
# <a name="icordebugthread2-interface"></a>Интерфейс ICorDebugThread2

Служит логическим расширением интерфейса ICorDebugThread.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetActiveFunctions](icordebugthread2-getactivefunctions-method.md)|Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.|  
|[Метод GetConnectionID](icordebugthread2-getconnectionid-method.md)|Возвращает идентификатор соединения для этого `ICorDebugThread2` .|  
|[Метод GetTaskID](icordebugthread2-gettaskid-method.md)|Возвращает идентификатор задачи для этого `ICorDebugThread2` .|  
|[Метод GetVolatileOSThreadID](icordebugthread2-getvolatileosthreadid-method.md)|Возвращает идентификатор потока операционной системы для этого `ICorDebugThread2` .|  
|[Метод InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md)|Позволяет отладчику перехватывать текущее исключение в потоке.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
