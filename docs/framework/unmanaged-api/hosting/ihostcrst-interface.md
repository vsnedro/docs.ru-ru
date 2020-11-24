---
title: Интерфейс IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 350af708456914c73929d2b8887173cf784d4294
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680564"
---
# <a name="ihostcrst-interface"></a>Интерфейс IHostCrst

Служит в качестве представления критической секции для потоков в основном приложении.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Enter](ihostcrst-enter-method.md)|Входит в критическую секцию.|  
|[Метод Leave](ihostcrst-leave-method.md)|Оставляет критическую секцию.|  
|[Метод SetSpinCount](ihostcrst-setspincount-method.md)|Задает счетчик счетчиков для критической секции.|  
|[Метод TryEnter](ihostcrst-tryenter-method.md)|Пытается войти в критическую секцию и немедленно сообщает об успешном или неуспешном завершении.|  
  
## <a name="remarks"></a>Комментарии  

 `IHostCrst` позволяет среде CLR взаимодействовать непосредственно с представлением критического раздела узла, а не использовать функции Win32, такие как `EnterCriticalSection` или `LeaveCriticalSection` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
