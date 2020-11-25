---
title: Метод ICorProfilerCallback::ThreadDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: 0cef868861155d553aba42fe28c3f1f1b86763b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731973"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a>Метод ICorProfilerCallback::ThreadDestroyed

Уведомляет профилировщик о том, что поток был уничтожен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Параметры  

 `threadId`  
 окне Идентификатор уничтоженного потока.  
  
## <a name="remarks"></a>Комментарии  

 `threadId`Значение больше не является допустимым во время этого вызова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ThreadCreated](icorprofilercallback-threadcreated-method.md)
