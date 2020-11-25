---
title: Метод ICorDebugManagedCallback2::DestroyConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720117"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a>Метод ICorDebugManagedCallback2::DestroyConnection

Уведомляет отладчик о завершении указанного соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pProcess`  
 окне Указатель на объект ICorDebugProcess, представляющий процесс, содержащий удаленное соединение.  
  
 `dwConnectionId`  
 окне Идентификатор уничтоженного соединения.  
  
## <a name="remarks"></a>Комментарии  

 `DestroyConnection`Обратный вызов будет срабатывать, когда узел вызывает [ICLRDebugManager:: ЕНДКОННЕКТИОН](../hosting/iclrdebugmanager-endconnection-method.md) в [API размещения](../hosting/index.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
