---
title: Интерфейс IHostTask
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 10efe853c9a7ad7676058bc01b07063c557623d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699226"
---
# <a name="ihosttask-interface"></a>Интерфейс IHostTask

Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alert](ihosttask-alert-method.md)|Запрашивает выход узла из задачи, представленной текущим `IHostTask` экземпляром, поэтому задачу можно прервать.|  
|[Метод GetPriority](ihosttask-getpriority-method.md)|Возвращает уровень приоритета потока задачи, представленной текущим `IHostTask` экземпляром.|  
|[Метод Join](ihosttask-join-method.md)|Блокирует вызывающую задачу до тех пор, пока задача, представленная текущим `IHostTask` экземпляром, не завершится, истечет указанный интервал времени, или будет вызван метод [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|[Метод SetCLRTask](ihosttask-setclrtask-method.md)|Связывает экземпляр [интерфейса ICLRTask](iclrtask-interface.md) с текущим `IHostTask` экземпляром.|  
|[Метод SetPriority](ihosttask-setpriority-method.md)|Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим `IHostTask` экземпляром.|  
|[Метод Start](ihosttask-start-method.md)|Запрашивает, что узел перемещает задачу, представленную текущим `IHostTask` экземпляром, из приостановленного состояния в активное состояние, в котором может выполняться код.|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR вызывает методы, определенные `IHostTask` для запуска задачи, установки ее уровня приоритета и т. д.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
