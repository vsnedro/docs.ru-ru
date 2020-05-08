---
title: Метод ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: c2e8aaa2774e3e2699a73c40804391ca245047b1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976594"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>Метод ICorDebugController::SetAllThreadsDebugState
Задает состояние отладки всех управляемых потоков в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `state`  
 окне Значение перечисления "Кордебугсреадстате", указывающее состояние потока для отладки.  
  
 `pExceptThisThread`  
 окне Указатель на объект "ICorDebugThread", представляющий поток, исключаемый из параметра состояния отладки. Если это значение равно null, ни один поток не исключен.  
  
## <a name="remarks"></a>Remarks  
 Метод может влиять на потоки, которые не видны через [метод енумератесреадс](icordebugcontroller-enumeratethreads-method.md), поэтому потоки, которые были приостановлены с `SetAllThreadsDebugState` помощью метода, необходимо возобновить с `SetAllThreadsDebugState` помощью метода. `SetAllThreadsDebugState`  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
