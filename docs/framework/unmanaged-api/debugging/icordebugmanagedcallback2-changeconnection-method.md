---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback2:: Чанжеконнектион'
title: Метод ICorDebugManagedCallback2::ChangeConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 854ea7f40cad9bce613b4034afe7688f4aaf4e52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790923"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>Метод ICorDebugManagedCallback2::ChangeConnection

Уведомляет отладчик о том, что набор задач, связанных с указанным соединением, изменился.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pProcess`  
 окне Указатель на объект "ICorDebugProcess", представляющий процесс, содержащий измененное соединение.  
  
 `dwConnectionId`  
 окне Идентификатор измененного соединения.  
  
## <a name="remarks"></a>Remarks  

 `ChangeConnection`Обратный вызов будет срабатывать в одном из следующих случаев.  
  
- При присоединении отладчика к процессу, который содержит соединения. В этом случае среда выполнения создаст и отправит событие [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) и `ChangeConnection` событие для каждого соединения в процессе. `ChangeConnection`Событие создается для каждого существующего соединения независимо от того, изменился ли набор задач этого соединения с момента его создания.  
  
- Когда узел вызывает [ICLRDebugManager:: SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) в [API размещения](../hosting/index.md).  
  
 Отладчик должен проверить все потоки в процессе, чтобы получить новые изменения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
