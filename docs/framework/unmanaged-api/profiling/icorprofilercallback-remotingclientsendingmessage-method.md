---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: RemotingClientSendingMessage'
title: Метод ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
ms.openlocfilehash: 3d075b3f3c3ffe63c9d4401bdc182037593b5b19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788934"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a>Метод ICorProfilerCallback::RemotingClientSendingMessage

Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Параметры  

 `pCookie`  
 окне Значение, которое соответствует значению, указанному в параметре [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) в следующих условиях:  
  
- Файлы Cookie GUID удаленного взаимодействия активны.  
  
- Канал проходит успешную передачу сообщения.  
  
- Файлы Cookie GUID активны в процессе на стороне сервера.  
  
 Это позволяет легко связывать вызовы удаленного взаимодействия и создавать логические стеки вызовов.  
  
 `fIsAsync`  
 окне Значение, равное, `true` Если вызов является асинхронным; в противном случае — `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
