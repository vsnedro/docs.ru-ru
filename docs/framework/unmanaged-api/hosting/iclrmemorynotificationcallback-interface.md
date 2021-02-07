---
description: 'Дополнительные сведения о: интерфейс ICLRMemoryNotificationCallback'
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
ms.openlocfilehash: 46e53cdf0b7f797b8945237d47fc3b521b08ddb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689243"
---
# <a name="iclrmemorynotificationcallback-interface"></a>Интерфейс ICLRMemoryNotificationCallback

Позволяет узлу сообщать об условиях нехватки памяти с помощью подхода, аналогичного функции Win32 `CreateMemoryResourceNotification` .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)|Уведомляет среду CLR о загрузке памяти на компьютере.|  
  
## <a name="remarks"></a>Remarks  

 Узел использует `ICLRMemoryNotificationCallback` интерфейс для запроса освобождения ресурсов памяти CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
