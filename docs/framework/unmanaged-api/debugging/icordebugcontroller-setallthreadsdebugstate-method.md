---
description: 'Дополнительные сведения о методе: ICorDebugController:: SetAllThreadsDebugState'
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
ms.openlocfilehash: 3bce5360833ae18c68bc8d7ea24f0dec7615f7a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710742"
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

 `SetAllThreadsDebugState`Метод может влиять на потоки, которые не видны через [метод енумератесреадс](icordebugcontroller-enumeratethreads-method.md), поэтому потоки, которые были приостановлены с помощью метода, `SetAllThreadsDebugState` необходимо возобновить с помощью `SetAllThreadsDebugState` метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
