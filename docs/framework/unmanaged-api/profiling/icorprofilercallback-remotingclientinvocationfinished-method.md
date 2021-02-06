---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: Ремотингклиентинвокатионфинишед'
title: Метод ICorProfilerCallback::RemotingClientInvocationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: bc15139e10b7634c50604d9a05ba290566145c21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648016"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>Метод ICorProfilerCallback::RemotingClientInvocationFinished

Уведомляет профилировщик о том, что вызов удаленного взаимодействия был выполнен до завершения на клиенте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Remarks  

 Если вызов удаленного взаимодействия был синхронным, он также выполняется до завершения на сервере. Если вызов удаленного взаимодействия был асинхронным, то при обработке вызова может быть по-прежнему ожидаемый ответ. Если ожидается ответ, он будет выполняться как вызов метода [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) и дополнительный вызов метода `RemotingClientInvocationFinished` для указания необходимой дополнительной обработки асинхронного вызова.  
  
 Каждая из следующих пар обратных вызовов будет выполняться в одном потоке:  
  
- `RemotingClientInvocationStarted` и [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) и [ICorProfilerCallback:: ремотингклиентинвокатионфинишед](icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) и [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)  
  
 При использовании обратных вызовов удаленного взаимодействия следует учитывать следующие моменты.  
  
- Выполнение функции удаленного взаимодействия не отражается API-интерфейсом профилировщика, поэтому уведомления для функций, которые вызываются из клиента и выполняются на сервере, не получаются должным образом. Фактический вызов происходит через прокси-объект; для профилировщика отображается, что определенные функции JIT-скомпилированы, но никогда не используются.  
  
- Профилировщик не получает точные уведомления о событиях асинхронного удаленного взаимодействия.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
