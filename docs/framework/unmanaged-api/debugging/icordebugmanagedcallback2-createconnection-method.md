---
title: Метод ICorDebugManagedCallback2::CreateConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: 5a4ebf65dfaaa487e87f3fd78e54c468c7e24a89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697250"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>Метод ICorDebugManagedCallback2::CreateConnection

Уведомляет отладчик о создании нового соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pProcess`  
 окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором было создано соединение  
  
 `dwConnectionId`  
 окне Идентификатор нового соединения.  
  
 `pConnName`  
 окне Указатель на имя нового соединения.  
  
## <a name="remarks"></a>Комментарии  

 `CreateConnection`Обратный вызов будет срабатывать в одном из следующих случаев.  
  
- При присоединении отладчика к процессу, который содержит соединения. В этом случае среда выполнения создаст и отправит `CreateConnection` событие и событие [ICorDebugManagedCallback2:: чанжеконнектион](icordebugmanagedcallback2-changeconnection-method.md) для каждого соединения в процессе.  
  
- Когда узел вызывает [ICLRDebugManager:: бегинконнектион](../hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../hosting/index.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
