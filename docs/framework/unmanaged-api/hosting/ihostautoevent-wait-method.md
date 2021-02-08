---
description: 'Дополнительные сведения о методе: Ихостаутоевент:: wait'
title: Метод IHostAutoEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: 0b75b44075dda46a3d84850cebd6b8f3851b055c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789480"
---
# <a name="ihostautoeventwait-method"></a>Метод IHostAutoEvent::Wait

Приводит к тому, что текущий экземпляр [ихостаутоевент](ihostautoevent-interface.md) ожидает его признания или истечения указанного периода времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwMilliseconds`  
 окне Число миллисекунд, в течение которых текущий `IHostAutoEvent` экземпляр должен ожидать перед возвратом, если ни один из потоков или волокон не получает владение.  
  
 `option`  
 окне Одно из значений [WAIT_OPTION](wait-option-enumeration.md) , определяющее действие, которое должен выполнить узел, если эта операция блокируется.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`Wait` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_DEADLOCK|Узел обнаружил взаимоблокировку в течение интервала ожидания и выбрал событие, представленное текущим `IHostAutoEvent` экземпляром в качестве жертвы взаимоблокировки.|  
  
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
