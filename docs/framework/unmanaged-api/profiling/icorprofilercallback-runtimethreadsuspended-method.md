---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: RuntimeThreadSuspended'
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
ms.openlocfilehash: f7c2f5baf5a320375d9a2606ca05b13d522336be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657337"
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
  
## <a name="remarks"></a>Remarks  

 Это `RuntimeThreadSuspended` уведомление может возникнуть в любое время между методами [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) и связанными обратными вызовами [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) . Уведомления, которые происходят между [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted` предназначены для потоков, которые были запущены в неуправляемом коде и были приостановлены при входе в среду выполнения.  
  
 Как правило, этот обратный вызов происходит сразу после приостановки потока. Однако если текущий выполняющийся поток (поток, вызвавший этот обратный вызов) является приостановленным, этот обратный вызов произойдет непосредственно перед приостановкой потока.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)
