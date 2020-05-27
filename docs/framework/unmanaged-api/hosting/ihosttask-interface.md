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
ms.openlocfilehash: f8f476f681764a46700dd5ec83c8f9b2739f18f6
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842495"
---
# <a name="ihosttask-interface"></a>Интерфейс IHostTask
Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alert](ihosttask-alert-method.md)|Запрашивает выход узла из задачи, представленной текущим `IHostTask` экземпляром, поэтому задачу можно прервать.|  
|[Метод GetPriority](ihosttask-getpriority-method.md)|Возвращает уровень приоритета потока задачи, представленной текущим `IHostTask` экземпляром.|  
|[Метод Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Блокирует вызывающую задачу до тех пор, пока задача, представленная текущим `IHostTask` экземпляром, не завершится, истечет указанный интервал времени, или будет вызван метод [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|[Метод SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Связывает экземпляр [интерфейса ICLRTask](iclrtask-interface.md) с текущим `IHostTask` экземпляром.|  
|[Метод SetPriority](ihosttask-setpriority-method.md)|Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим `IHostTask` экземпляром.|  
|[Метод Start](ihosttask-start-method.md)|Запрашивает, что узел перемещает задачу, представленную текущим `IHostTask` экземпляром, из приостановленного состояния в активное состояние, в котором может выполняться код.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает методы, определенные `IHostTask` для запуска задачи, установки ее уровня приоритета и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
