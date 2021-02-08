---
description: 'Дополнительные сведения о методе: ICLRSyncManager:: Жетрвлокковнернекст'
title: Метод ICLRSyncManager::GetRWLockOwnerNext
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
ms.openlocfilehash: f49bdd5065ac896147967c0a013347ab39ce1eff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785004"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a>Метод ICLRSyncManager::GetRWLockOwnerNext

Возвращает следующий экземпляр [IHostTask](ihosttask-interface.md) , заблокированный для текущей блокировки чтения и записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `Iterator`  
 окне Итератор, который был создан с помощью вызова [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).  
  
 `ppOwnerHostTask`  
 заполняет Указатель на следующий объект `IHostTask` , ожидающий блокировки, или значение null, если ни одна из задач не ожидает выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetRWLockOwnerNext` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Если параметр `ppOwnerHostTask` имеет значение null, итерация завершается и узел должен вызвать метод [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
> [!NOTE]
> Среда CLR вызывает метод в `AddRef` , `IHostTask` который `ppOwnerHostTask` указывает, чтобы предотвратить выход этой задачи, пока узел удерживает указатель. Узел должен вызвать `Release` , чтобы уменьшить число ссылок по завершении.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
