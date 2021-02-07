---
description: 'Дополнительные сведения о: интерфейс IHostSemaphore'
title: Интерфейс IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 682f1f70925310e93f88f1dc314052e801a5e87b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671364"
---
# <a name="ihostsemaphore-interface"></a>Интерфейс IHostSemaphore

Представляет реализацию семафора для потоков в ведущем приложении.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)|Увеличивает количество текущего `IHostSemaphore` экземпляра на указанный объем.|  
|[Метод Wait](ihostsemaphore-wait-method.md)|Вызывает `IHostSemaphore` Ожидание текущего экземпляра до его признания или указанного периода времени.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostAutoEvent](ihostautoevent-interface.md)
- [Интерфейс IHostManualEvent](ihostmanualevent-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
