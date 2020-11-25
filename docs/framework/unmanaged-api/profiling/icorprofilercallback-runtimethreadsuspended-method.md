---
title: Метод ICorProfilerCallback::RuntimeThreadSuspended
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: 33a39cf2781f49ff0e31989831c4c9829889ec3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732006"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>Метод ICorProfilerCallback::RuntimeThreadSuspended

Уведомляет профилировщик о том, что указанный поток был приостановлен или готов к приостановке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Параметры  

 `threadId`  
 окне Идентификатор приостановленного потока.  
  
## <a name="remarks"></a>Комментарии  

 Это `RuntimeThreadSuspended` уведомление может возникнуть в любое время между методами [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) и связанными обратными вызовами [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) . Уведомления, которые происходят между [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted` предназначены для потоков, которые были запущены в неуправляемом коде и были приостановлены при входе в среду выполнения.  
  
 Как правило, этот обратный вызов происходит сразу после приостановки потока. Однако если текущий выполняющийся поток (поток, вызвавший этот обратный вызов) является приостановленным, этот обратный вызов произойдет непосредственно перед приостановкой потока.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)
