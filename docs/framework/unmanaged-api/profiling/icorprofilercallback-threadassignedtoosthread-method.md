---
title: Метод ICorProfilerCallback::ThreadAssignedToOSThread
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 2d6f34d88dd79fe350f1c018e3afa55e5b180c46
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732012"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a>Метод ICorProfilerCallback::ThreadAssignedToOSThread

Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a>Параметры  

 `managedThreadId`  
 окне Идентификатор управляемого потока.  
  
 `osThreadId`  
 окне Идентификатор потока операционной системы.  
  
## <a name="remarks"></a>Комментарии  

 `ThreadAssignedToOSThread`Обратный вызов существует, чтобы профилировщик мог поддерживать точное сопоставление по волокнам потоков операционной системы с управляемыми потоками.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
