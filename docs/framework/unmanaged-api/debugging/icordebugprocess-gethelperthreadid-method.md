---
title: Метод ICorDebugProcess::GetHelperThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
ms.openlocfilehash: 77cc658e28c7a69d8c4aeeed2f3e7ea40f0d2af6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724576"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>Метод ICorDebugProcess::GetHelperThreadID

Получает идентификатор потока операционной системы (ОС) внутреннего вспомогательного потока отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pThreadID`  
 заполняет Указатель на идентификатор потока операционной системы внутреннего вспомогательного потока отладчика.  
  
## <a name="remarks"></a>Комментарии  

 Во время управляемой и неуправляемой отладки следует следить за тем, чтобы поток с указанным ИДЕНТИФИКАТОРом оставался в работоспособном режиме, если он достигнет точки останова, размещенной отладчиком. Отладчику также может потребоваться скрыть этот поток от пользователя. Если в процессе еще не существует вспомогательного потока, `GetHelperThreadID` метод возвращает ноль в * `pThreadID` .  
  
 Невозможно кэшировать идентификатор потока вспомогательного потока, так как он может измениться со временем. Необходимо повторно запросить идентификатор потока при каждом событии остановки.  
  
 Идентификатор потока вспомогательного потока отладчика будет правильным для каждого неуправляемого события [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) , что позволяет отладчику определить идентификатор потока вспомогательного потока и скрыть его от пользователя. Поток, идентифицированный в виде вспомогательного потока во время неуправляемого `ICorDebugManagedCallback::CreateThread` события, никогда не будет запускать управляемый пользовательский код.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl. CorDebug. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
