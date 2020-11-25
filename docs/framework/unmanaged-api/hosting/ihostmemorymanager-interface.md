---
title: Интерфейс IHostMemoryManager
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: 0f71e4c45e43c2027b12998532f2b04401a51951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731336"
---
# <a name="ihostmemorymanager-interface"></a>Интерфейс IHostMemoryManager

Предоставляет методы, позволяющие среде CLR выполнять запросы к виртуальной памяти через основное приложение вместо использования стандартных функций виртуальной памяти Win32.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AcquiredVirtualAddressSpace](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Уведомляет узел о том, что среда CLR получила указанную память из операционной системы.|  
|[Метод CreateMAlloc](ihostmemorymanager-createmalloc-method.md)|Возвращает указатель интерфейса на экземпляр [IHostMAlloc](ihostmalloc-interface.md) , который используется для запроса выделения памяти из кучи, созданного узлом.|  
|[Метод GetMemoryLoad](ihostmemorymanager-getmemoryload-method.md)|Возвращает объем используемой в данный момент физической памяти, сообщаемой узлом.|  
|[Метод NeedsVirtualAddressSpace](ihostmemorymanager-needsvirtualaddressspace-method.md)|Уведомляет узел о том, что среда CLR будет пытаться использовать указанную память.|  
|[Метод RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md)|Регистрирует указатель на функцию обратного вызова, которая вызывается хостом для уведомления среды CLR о текущей загрузке памяти на компьютере.|  
|[Метод ReleasedVirtualAddressSpace](ihostmemorymanager-releasedvirtualaddressspace-method.md)|Уведомляет узел о том, что среда CLR завершила работу с заданной памятью.|  
|[Метод VirtualAlloc](ihostmemorymanager-virtualalloc-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая резервирует или фиксирует область страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[Метод VirtualFree](ihostmemorymanager-virtualfree-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая выдает, выдает или освобождает и отменяет выделение области страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[Метод VirtualProtect](ihostmemorymanager-virtualprotect-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[Метод VirtualQuery](ihostmemorymanager-virtualquery-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.|  
  
## <a name="remarks"></a>Комментарии  

 `IHostMemoryManager` также предоставляет методы для среды CLR для получения указателя, с помощью которого можно выполнять запросы к памяти в куче и получать уровень нехватки памяти в процессе, сообщаемый узлом.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IHostMalloc](ihostmalloc-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
