---
title: Метод ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 0d36390a905561b64b3ca6ca95722f82158450be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695222"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>Метод ICorDebugProcess::ClearCurrentException

Очищает текущее неуправляемое исключение для данного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Параметры  

 `threadID`  
 окне Идентификатор потока, в котором будет очищаться текущее неуправляемое исключение.  
  
## <a name="remarks"></a>Комментарии  

 Вызывайте этот метод перед вызовом [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , когда поток сообщил о неуправляемом исключении, которое должно игнорироваться отлаживаемым объектом. Это приведет к удалению необработанных внутренних () и нестандартных событий (OOB) для данного потока. Все точки останова OOB и одношаговые исключения автоматически очищаются.  
  
 Используйте [ICorDebugThread2:: интерцепткуррентексцептион](icordebugthread2-interceptcurrentexception-method.md) для перехвата текущего управляемого исключения в потоке.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
