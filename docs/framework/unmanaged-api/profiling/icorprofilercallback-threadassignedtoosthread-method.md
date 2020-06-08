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
ms.openlocfilehash: 182a82300183046ccb4a93a79af0dd8f23848c20
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503183"
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
  
## <a name="remarks"></a>Примечания  
 `ThreadAssignedToOSThread`Обратный вызов существует, чтобы профилировщик мог поддерживать точное сопоставление по волокнам потоков операционной системы с управляемыми потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
