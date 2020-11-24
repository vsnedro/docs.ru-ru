---
title: Метод ICLRSyncManager::GetMonitorOwner
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: a2cb82d8071518af4d4bc3276871f3846a5a5693
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687090"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>Метод ICLRSyncManager::GetMonitorOwner

Возвращает экземпляр [IHostTask](ihosttask-interface.md) , которому принадлежит монитор, идентифицируемый указанным файлом cookie.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cookie`  
 окне Файл cookie, связанный с монитором.  
  
 `ppOwnerHostTask`  
 заполняет Указатель на объект `IHostTask` , который в данный момент владеет монитором, или значение null, если ни одна задача не владеет.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 Узел обычно вызывается `GetMonitorOwner` как часть механизма обнаружения взаимоблокировки. Файл cookie связывается с монитором при его создании с помощью вызова [метод ihostsyncmanager:: CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).  
  
> [!NOTE]
> Вызов для освобождения события, лежащего в основе монитора, может блокироваться, но не будет взаимоблокировками, если вызов этого метода в настоящее время действует на файл cookie, связанный с этим монитором. Другие задачи также могут блокироваться при попытке получить этот монитор.  
  
 `GetMonitorOwner` всегда возвращает значение немедленно и может вызываться в любое время после вызова `CreateMonitorEvent` . Узлу не нужно ждать, пока задача ожидает события.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
