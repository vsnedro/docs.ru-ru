---
title: Интерфейс ICLRTask
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: 419baaf64397830ef86cfd9e5c3437e3f5b57795
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763011"
---
# <a name="iclrtask-interface"></a>Интерфейс ICLRTask
Предоставляет методы, позволяющие основному приложению выполнять запросы среды CLR или предоставлять в среду CLR уведомление о связанной задаче.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](iclrtask-abort-method.md)|Требует, чтобы среда CLR прервала задачу, которую `ICLRTask` представляет текущий экземпляр.|  
|[Метод ExitTask](iclrtask-exittask-method.md)|Уведомляет среду CLR о том, что задача, связанная с текущим `ICLRTask` экземпляром, завершается, и пытается корректно завершить задачу.|  
|[Метод GetMemStats](iclrtask-getmemstats-method.md)|Возвращает статистические сведения об использовании ресурсов памяти задачей, представленной текущим `ICLRTask` экземпляром.|  
|[Метод LocksHeld](iclrtask-locksheld-method.md)|Возвращает количество блокировок, которые в настоящее время удерживаются в задаче.|  
|[Метод NeedsPriorityScheduling](iclrtask-needspriorityscheduling-method.md)|Возвращает значение, указывающее, должен ли узел назначить высокий приоритет для перепланирования задачи, представленной текущим `ICLRTask` экземпляром.|  
|[Метод Reset](iclrtask-reset-method.md)|Информирует среду CLR о том, что узел выполнил задачу, и позволяет среде CLR повторно использовать текущий `ICLRTask` экземпляр для представления другой задачи.|  
|[Метод RudeAbort](iclrtask-rudeabort-method.md)|Заставляет среду CLR немедленно прерывать задачу, представленную текущим `ICLRTask` экземпляром, без гарантии того, что методы завершения будут выполняться.|  
|[Метод SetTaskIdentifier](iclrtask-settaskidentifier-method.md)|Задает уникальный идентификатор для задачи, представленной текущим `ICLRTask` экземпляром, для использования при отладке.|  
|[Метод SwitchIn](iclrtask-switchin-method.md)|Уведомляет среду CLR о том, что задача, представленная текущим `ICLRTask` экземпляром, находится в рабочем состоянии.|  
|[Метод SwitchOut](iclrtask-switchout-method.md)|Уведомляет среду CLR о том, что задача, представленная текущим `ICLRTask` экземпляром, больше не находится в рабочем состоянии.|  
|[Метод YieldTask](iclrtask-yieldtask-method.md)|Запрашивает доступность процессорного времени средой CLR для выполнения других задач. Среда CLR не гарантирует, что задача будет переведена в состояние, в котором она может подать время на обработку.|  
  
## <a name="remarks"></a>Комментарии  
 `ICLRTask`Представляет собой представление задачи для среды CLR. В любой момент во время выполнения кода задача может быть описана как выполняется или ожидает выполнения. Узел вызывает метод, `ICLRTask::SwitchIn` чтобы уведомить среду CLR о том, что задача, которую `ICLRTask` представляет текущий экземпляр, теперь находится в рабочем состоянии. После вызова `ICLRTask::SwitchIn` узел может запланировать задачу в любом потоке операционной системы, за исключением случаев, когда среда выполнения требует сходство потоков, как указано вызовами методов [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) и [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) . Спустя некоторое время операционная система может решить удалить задачу из потока и перевести ее в неработающее состояние. Например, это может произойти, если задача блокирует примитивы синхронизации или ожидает завершения операций ввода-вывода. Узел вызывает [Переключение](iclrtask-switchout-method.md) , чтобы УВЕДОМИТЬ среду CLR о том, что задача, представленная текущим `ICLRTask` экземпляром, больше не находится в рабочем состоянии.  
  
 Обычно задача завершается в конце выполнения кода. В это время узел вызывает `ICLRTask::ExitTask` для уничтожения связанного `ICLRTask` . Однако задачи можно также перезапускать с помощью вызова метода `ICLRTask::Reset` , который позволяет `ICLRTask` повторно использовать экземпляр. Такой подход предотвращает издержки на многократное создание и уничтожение экземпляров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Интерфейс ICLRTask2](iclrtask2-interface.md)
