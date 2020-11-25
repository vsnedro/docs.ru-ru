---
title: Интерфейс IHostSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: 8a5fc42191634a2e5a441baecc4b78212ffad687
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720501"
---
# <a name="ihostsyncmanager-interface"></a>Интерфейс IHostSyncManager

Предоставляет методы, позволяющие среде CLR создавать примитивы синхронизации путем вызова узла вместо использования функций синхронизации Win32.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateAutoEvent](ihostsyncmanager-createautoevent-method.md)|Создает объект события автоматического сброса.|  
|[Метод CreateCrst](ihostsyncmanager-createcrst-method.md)|Создает объект критической секции для синхронизации.|  
|[Метод CreateCrstWithSpinCount](ihostsyncmanager-createcrstwithspincount-method.md)|Создает объект критической секции с количеством счетчиков для синхронизации.|  
|[Метод CreateManualEvent](ihostsyncmanager-createmanualevent-method.md)|Создает объект события ручного сброса.|  
|[Метод CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md)|Создает Отслеживаемый объект события автоматического сброса.|  
|[Метод CreateRWLockReaderEvent](ihostsyncmanager-createrwlockreaderevent-method.md)|Создает объект события ручного сброса для реализации блокировки чтения.|  
|[Метод CreateRWLockWriterEvent](ihostsyncmanager-createrwlockwriterevent-method.md)|Создает объект события автоматического сброса для реализации блокировки модуля записи.|  
|[Метод CreateSemaphore](ihostsyncmanager-createsemaphore-method.md)|Создает объект [IHostSemaphore](ihostsemaphore-interface.md) для среды CLR, который будет использоваться в качестве семафора для событий ожидания.|  
|[Метод SetCLRSyncManager](ihostsyncmanager-setclrsyncmanager-method.md)|Задает экземпляр [ICLRSyncManager](iclrsyncmanager-interface.md) , связываемый с текущим `IHostSyncManager` экземпляром.|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR обнаруживает реализацию узла `IHostSyncManager` , вызывая метод [IHostControl:: жесостманажер](ihostcontrol-gethostmanager-method.md) с `IID` IID_IHostSyncManager.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
