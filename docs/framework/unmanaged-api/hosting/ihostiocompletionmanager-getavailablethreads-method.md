---
title: Метод IHostIoCompletionManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: 3e9f4e98962532efe4b2e2a779add841b7b3a835
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724264"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a>Метод IHostIoCompletionManager::GetAvailableThreads

Возвращает количество потоков завершения ввода-вывода из общего числа потоков, управляемых узлом, которые в настоящее время не обслуживают запросы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwAvailableIoCompletionThreads`  
 заполняет Указатель на число потоков завершения ввода-вывода, управляемых узлом, которые в настоящее время доступны для запросов на обслуживание.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetAvailableThreads` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не предоставляет реализацию `GetAvailableThreads` .|  
  
## <a name="remarks"></a>Комментарии  

 Ведущему приложению может потребоваться монопольный контроль над размером пула потоков завершения ввода-вывода по таким причинам, как реализация, производительность или масштабируемость. Таким образом, хосту не требуется реализовывать `GetAvailableThreads` . В этом случае узел должен вернуть E_NOTIMPL из этого метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Интерфейс IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
