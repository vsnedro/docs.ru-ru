---
description: 'Дополнительные сведения о: интерфейс IHostCrst'
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
ms.openlocfilehash: 7945f0087667c1d610a1a2370528b055af74d579
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708883"
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
  
## <a name="remarks"></a>Remarks  

 `IHostCrst` позволяет среде CLR взаимодействовать непосредственно с представлением критического раздела узла, а не использовать функции Win32, такие как `EnterCriticalSection` или `LeaveCriticalSection` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
