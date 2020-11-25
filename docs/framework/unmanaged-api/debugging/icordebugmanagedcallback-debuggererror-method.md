---
title: Метод ICorDebugManagedCallback::DebuggerError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: eb95bf779e54742cd2cc4b688c24a49e6d85a40d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731908"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>Метод ICorDebugManagedCallback::DebuggerError

Уведомляет отладчик о том, что произошла ошибка при попытке выполнить обработку события из среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pProcess`  
 окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором произошло событие.  
  
 `errorHR`  
 окне Значение HRESULT, возвращенное обработчиком событий.  
  
 `errorCode`  
 окне Целое число, указывающее ошибку CLR.  
  
## <a name="remarks"></a>Комментарии  

 Процесс может быть помещен в сквозной режим в зависимости от характера ошибки.  
  
 `DebugError`Обратный вызов указывает, что службы отладки были отключены из-за ошибки, поэтому Отладчики должны сделать сообщение об ошибке доступным для пользователя. [ICorDebugProcess:: GetID](icordebugprocess-getid-method.md) будет использоваться в качестве безопасного вызова, но все остальные методы, включая [ICorDebug:: Terminate](icordebug-terminate-method.md), не должны вызываться. Отладчик должен использовать средства операционной системы для завершения процессов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
