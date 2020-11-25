---
title: Интерфейс ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: e23675351e1fd0de510243c9ee8b3a6dd6f29cec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714124"
---
# <a name="iclriocompletionmanager-interface"></a>Интерфейс ICLRIoCompletionManager

Реализует метод обратного вызова, который позволяет узлу уведомлять среду CLR о состоянии указанных запросов ввода-вывода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnComplete](iclriocompletionmanager-oncomplete-method.md)|Сообщает среде CLR о состоянии запроса ввода-вывода, сделанного с помощью вызова метода [IHostIoCompletionManager:: BIND](ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Комментарии  

 Узел реализует абстракцию завершения ввода-вывода с помощью интерфейса [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) . CLR выполняет запросы ввода-вывода через этот интерфейс, и узел уведомляет среду выполнения о результатах таких запросов с помощью `ICLRIoCompletionManager` интерфейса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
- [Интерфейс IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
