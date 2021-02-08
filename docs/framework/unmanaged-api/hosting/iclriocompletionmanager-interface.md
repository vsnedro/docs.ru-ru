---
description: 'Дополнительные сведения о: интерфейс ICLRIoCompletionManager'
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
ms.openlocfilehash: b2d18f9c9900d448f0c6517520c303eb4258f8d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789897"
---
# <a name="iclriocompletionmanager-interface"></a>Интерфейс ICLRIoCompletionManager

Реализует метод обратного вызова, который позволяет узлу уведомлять среду CLR о состоянии указанных запросов ввода-вывода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnComplete](iclriocompletionmanager-oncomplete-method.md)|Сообщает среде CLR о состоянии запроса ввода-вывода, сделанного с помощью вызова метода [IHostIoCompletionManager:: BIND](ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Remarks  

 Узел реализует абстракцию завершения ввода-вывода с помощью интерфейса [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) . CLR выполняет запросы ввода-вывода через этот интерфейс, и узел уведомляет среду выполнения о результатах таких запросов с помощью `ICLRIoCompletionManager` интерфейса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
- [Интерфейс IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
