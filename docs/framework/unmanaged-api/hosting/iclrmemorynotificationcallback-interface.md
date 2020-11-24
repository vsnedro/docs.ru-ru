---
title: Интерфейс ICLRMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689541"
---
# <a name="iclrmemorynotificationcallback-interface"></a>Интерфейс ICLRMemoryNotificationCallback

Позволяет узлу сообщать об условиях нехватки памяти с помощью подхода, аналогичного функции Win32 `CreateMemoryResourceNotification` .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)|Уведомляет среду CLR о загрузке памяти на компьютере.|  
  
## <a name="remarks"></a>Комментарии  

 Узел использует `ICLRMemoryNotificationCallback` интерфейс для запроса освобождения ресурсов памяти CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
