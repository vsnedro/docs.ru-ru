---
title: Интерфейс IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804597"
---
# <a name="ihostmanualevent-interface"></a>Интерфейс IHostManualEvent
Предоставляет реализацию представления события ручного сброса в узле.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Reset](ihostmanualevent-reset-method.md)|Сбрасывает текущий `IHostManualEvent` экземпляр в несигнальное состояние.|  
|[Метод Set](ihostmanualevent-set-method.md)|Устанавливает для текущего `IHostManualEvent` экземпляра сигнальное состояние.|  
|[Метод Wait](ihostmanualevent-wait-method.md)|Вызывает `IHostManualEvent` Ожидание текущего экземпляра до его признания или истечения указанного периода времени.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostAutoEvent](ihostautoevent-interface.md)
- [Интерфейс IHostSemaphore](ihostsemaphore-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
