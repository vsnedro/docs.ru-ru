---
title: Метод ICorProfilerCallback::RuntimeSuspendAborted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: a3fb5c398b8ccd7caba0b005bcf03e64ecef4ba5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503254"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a>Метод ICorProfilerCallback::RuntimeSuspendAborted
Уведомляет профилировщик о том, что среда выполнения прервал приостановленную приостановку среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a>Примечания  
 Приостановка во время выполнения может быть прервана, если два потока одновременно пытаются приостановить выполнение.  
  
 Обратный вызов [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) или `RuntimeSuspendAborted` обратный вызов будет выполняться в одном потоке после обратного вызова [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) .  
  
 `RuntimeSuspendAborted`Обратный вызов гарантированно выполняется в том же потоке, что и `RuntimeSuspendStarted` обратный вызов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
