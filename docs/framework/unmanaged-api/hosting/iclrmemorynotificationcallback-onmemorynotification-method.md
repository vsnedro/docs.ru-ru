---
description: 'Дополнительные сведения о методе: ICLRMemoryNotificationCallback:: OnMemoryNotification'
title: Метод ICLRMemoryNotificationCallback::OnMemoryNotification
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
ms.openlocfilehash: 92041c433fa82bb63afda7968eb8c6e1fa72acb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789919"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a>Метод ICLRMemoryNotificationCallback::OnMemoryNotification

Уведомляет среду CLR о загрузке памяти на компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `eMemoryAvailable`  
 окне Одно из значений [емеморяваилабле](ememoryavailable-enumeration.md) , указывающее на нехватку памяти в данный момент на компьютере.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`OnMemoryNotification` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Среда CLR регистрирует обратный вызов с `OnMemoryNotification` помощью вызова метода [IHostMemoryManager:: RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md) . Среда выполнения использует сведения, возвращаемые при обратном вызове, чтобы освободить дополнительную память, когда узел сообщает, что ресурсы памяти имеют низкий уровень.  
  
> [!NOTE]
> Вызовы `OnMemoryNotification` никогда не блокируются. Они всегда возвращают немедленно.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
- [Метод RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md)
- [Интерфейс ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md)
