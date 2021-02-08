---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback2::D Естройконнектион'
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
ms.openlocfilehash: f17def5599dc02ed6b7b49d7f8ed4db02eb40181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790897"
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
  
## <a name="remarks"></a>Remarks  

 `DestroyConnection`Обратный вызов будет срабатывать, когда узел вызывает [ICLRDebugManager:: ЕНДКОННЕКТИОН](../hosting/iclrdebugmanager-endconnection-method.md) в [API размещения](../hosting/index.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
