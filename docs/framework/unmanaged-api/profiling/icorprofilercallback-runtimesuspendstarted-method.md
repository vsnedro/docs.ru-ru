---
title: Метод ICorProfilerCallback::RuntimeSuspendStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: cc01254d9604ce39c964c7d78059ef4087483c77
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503228"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>Метод ICorProfilerCallback::RuntimeSuspendStarted
Уведомляет профилировщик о том, что среда выполнения собирается приостановить все потоки среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>Параметры  
 `suspendReason`  
 окне Значение перечисления [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) , указывающее причину приостановки.  
  
## <a name="remarks"></a>Примечания  
 Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения. На этом этапе они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу. Это также относится к новым потокам, которые вводят среду выполнения. Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже находятся в коде для преобразования, либо если они запросят приостановить работу в случае, если они достигают кода источника.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)
- [Метод RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)
