---
description: 'Дополнительные сведения о: интерфейс ICorDebugManagedCallback3'
title: Интерфейс ICorDebugManagedCallback3
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: 9fb3d44b1d793935ac997e8e4d8d86de4466f7b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801193"
---
# <a name="icordebugmanagedcallback3-interface"></a>Интерфейс ICorDebugManagedCallback3

Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CustomNotification](icordebugmanagedcallback3-customnotification-method.md)|Указывает, что создано включенное пользовательское уведомление отладчика.|  
  
## <a name="remarks"></a>Remarks  

 Этот интерфейс является логическим расширением интерфейсов [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) и [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
