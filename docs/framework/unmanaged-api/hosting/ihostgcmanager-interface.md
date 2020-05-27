---
title: Интерфейс IHostGCManager
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804859"
---
# <a name="ihostgcmanager-interface"></a>Интерфейс IHostGCManager
Предоставляет методы, которые уведомляют узел о событиях в механизме сборки мусора, реализованном средой CLR.  
  
## <a name="members"></a>Элементы  
  
|Член|Описание|  
|------------|-----------------|  
|[Метод SuspensionEnding](ihostgcmanager-suspensionending-method.md)|Уведомляет узел о том, что среда CLR возобновляет выполнение задач в потоках, которые были приостановлены для сборки мусора.|  
|[Метод SuspensionStarting](ihostgcmanager-suspensionstarting-method.md)|Уведомляет узел о том, что среда CLR приостанавливает выполнение задач, для выполнения сборки мусора.|  
|[Метод ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md)|Уведомляет узел о том, что поток, из которого был сделан вызов метода, собирается блокироваться для сборки мусора.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
