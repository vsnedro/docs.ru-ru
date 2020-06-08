---
title: Интерфейс ICorProfilerCallback2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
ms.openlocfilehash: 3b0e60602d2f36552c3e0e85ec51205b4128486b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499770"
---
# <a name="icorprofilercallback2-interface"></a>Интерфейс ICorProfilerCallback2
Предоставляет методы, которые используются средой CLR для уведомления профилировщика кода при возникновении событий, на которые подписан профилировщик. `ICorProfilerCallback2`Интерфейс является расширением интерфейса [ICorProfilerCallback](icorprofilercallback-interface.md) . То есть он предоставляет новые обратные вызовы, представленные в .NET Framework версии 2,0.  
  
> [!NOTE]
> Каждая реализация метода должна возвращать HRESULT со значением S_OK в случае успеха или E_FAIL при сбое. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемое каждым обратным вызовом, за исключением значения [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md)|Уведомляет профилировщик кода о том, что объект с методом завершения был помещен в очередь в поток метода завершения для выполнения своего `Finalize` метода.|  
|[Метод GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|Уведомляет профилировщик о завершении сборки мусора и выдачи всех обратных вызовов сборки мусора.|  
|[Метод GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)|Уведомляет профилировщик кода о начале сборки мусора.|  
|[Метод HandleCreated](icorprofilercallback2-handlecreated-method.md)|Уведомляет профилировщик кода о создании обработчика сборки мусора.|  
|[Метод HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)|Уведомляет профилировщик кода о том, что был уничтожен обработчик сборки мусора.|  
|[Метод RootReferences2](icorprofilercallback2-rootreferences2-method.md)|Уведомляет профилировщик о корневых ссылках после сборки мусора. Этот метод является расширением метода [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .|  
|[Метод SurvivingReferences](icorprofilercallback2-survivingreferences-method.md)|Уведомляет профилировщик о ссылках на объекты, которые были сохранившиются при сборке мусора.|  
|[Метод ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md)|Уведомляет профилировщик кода о том, что имя потока изменилось.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает метод в `ICorProfilerCallback` интерфейсе (или `ICorProfilerCallback2` ) для уведомления профилировщика при возникновении события, на которое подписан профилировщик. Это основной интерфейс обратного вызова, с помощью которого среда CLR взаимодействует с профилировщиком кода.  
  
 Профилировщик кода должен реализовывать методы `ICorProfilerCallback` интерфейса. Для .NET Framework 2,0 и более поздних версий профилировщик также должен реализовать `ICorProfilerCallback2` методы. Каждая реализация метода должна возвращать HRESULT со значением S_OK в случае успеха или E_FAIL при сбое. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемое каждым обратным вызовом, за исключением значения [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 Профилировщик кода должен быть зарегистрирован в реестре Microsoft Windows, его COM-объекте, который реализует `ICorProfilerCallback` интерфейсы и `ICorProfilerCallback2` . Профилировщик кода подписывается на события, для которых требуется получать уведомления путем вызова [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Обычно это делается в реализации метода [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)профилировщика. Затем профилировщик может получать уведомления от среды выполнения, когда событие собирается или было только что произошло в процессе выполнения.  
  
> [!NOTE]
> Профилировщик регистрирует один COM-объект. Если профилировщик предназначен для .NET Framework версии 1,0 или 1,1, этот COM-объект должен реализовывать только методы `ICorProfilerCallback` . Если он предназначен для .NET Framework версии 2,0 и более поздних, то COM-объект также должен реализовывать методы `ICorProfilerCallback2` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback3](icorprofilercallback3-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
