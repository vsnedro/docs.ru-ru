---
description: 'Дополнительные сведения о методе: IHostIoCompletionManager:: SetMinThreads'
title: Метод IHostIoCompletionManager::SetMinThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: aade5ebb9e318d51296e52e7cf1c31c6ea9e4f6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708246"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a>Метод IHostIoCompletionManager::SetMinThreads

Задает минимальное число потоков, которое узел должен выделить при завершении ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwMinIoCompletionThreads`  
 окне Минимальное число потоков завершения ввода-вывода, которые должен создать узел.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetMinThreads` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не предоставляет реализацию `SetMinThreads` .|  
  
## <a name="remarks"></a>Remarks  

 Узлу может потребоваться эксклюзивный контроль над количеством потоков, которые могут быть выделены для обработки запросов ввода-вывода, по таким причинам, как реализация, производительность или масштабируемость. По этой причине узел не является обязательным для реализации `SetMinThreads` . В этом случае узел должен вернуть E_NOTIMPL из этого метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Метод SetMaxThreads](ihostiocompletionmanager-setmaxthreads-method.md)
- [Интерфейс IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
