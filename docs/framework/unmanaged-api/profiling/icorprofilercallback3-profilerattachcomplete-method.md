---
title: Метод ICorProfilerCallback3::ProfilerAttachComplete
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: bcc938ff9322fca4f45366fdc695e0c3901484b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499666"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a>Метод ICorProfilerCallback3::ProfilerAttachComplete
Вызывается средой CLR для указания на то, что профилировщик теперь может вызывать методы перехвата [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) и [ICorProfilerInfo3:: EnumModules](icorprofilerinfo3-enummodules-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a>Примечания  
 `ProfilerAttachComplete`Обратный вызов выдается после вызова метода [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) . Он указывает следующее.  
  
- Обратные вызовы, которые были запрошены профилировщиком в `InitializeForAttach`, были активированы.  
  
- Профилировщик теперь может выполнять захват в связанных идентификаторах, не заботясь об отсутствующих уведомлениях.  
  
 Среда CLR игнорирует возвращаемое значение из этого обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
