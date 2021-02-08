---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback::D Ебугжереррор'
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
ms.openlocfilehash: 2f73e07711f7d2ce865aab8f90862563e767fd16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791010"
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
  
## <a name="remarks"></a>Remarks  

 Процесс может быть помещен в сквозной режим в зависимости от характера ошибки.  
  
 `DebugError`Обратный вызов указывает, что службы отладки были отключены из-за ошибки, поэтому Отладчики должны сделать сообщение об ошибке доступным для пользователя. [ICorDebugProcess:: GetID](icordebugprocess-getid-method.md) будет использоваться в качестве безопасного вызова, но все остальные методы, включая [ICorDebug:: Terminate](icordebug-terminate-method.md), не должны вызываться. Отладчик должен использовать средства операционной системы для завершения процессов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
