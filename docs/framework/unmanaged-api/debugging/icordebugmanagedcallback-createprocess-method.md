---
title: Метод ICorDebugManagedCallback::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: cd24e672c65769586dc618c21503dbb344566974
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731817"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a>Метод ICorDebugManagedCallback::CreateProcess

Уведомляет отладчик о том, что процесс был присоединен или запущен в первый раз.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pProcess`  
 окне Указатель на объект ICorDebugProcess, представляющий процесс, который был присоединен или запущен.  
  
## <a name="remarks"></a>Комментарии  

 Этот метод не вызывается до тех пор, пока не будет инициализирована среда CLR. Большая часть методов [ICorDebug](icordebug-interface.md) возвратит CORDBG_E_NOTREADY перед `CreateProcess` обратным вызовом.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
