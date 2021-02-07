---
description: 'Дополнительные сведения о методе: IHostIoCompletionManager:: Инитиализехостоверлаппед'
title: Метод IHostIoCompletionManager::InitializeHostOverlapped
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: 10be7edb67143937dec6efc6e35466466374d32d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708467"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>Метод IHostIoCompletionManager::InitializeHostOverlapped

Предоставляет узлу возможность инициализировать любые пользовательские данные, добавляемые в `OVERLAPPED` структуру Win32, которая используется для асинхронных запросов ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pvOverlapped`  
 окне Указатель на структуру Win32, `OVERLAPPED` которая будет включена в запрос ввода-вывода.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для выделения запрошенного ресурса.|  
  
## <a name="remarks"></a>Remarks  

 Функции платформы Windows используют `OVERLAPPED` структуру для хранения состояния асинхронных запросов ввода-вывода. Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить узлу возможность добавлять пользовательские данные в `OVERLAPPED` экземпляр.  
  
> [!IMPORTANT]
> Чтобы перейти к началу пользовательского блока данных, узлы должны задать смещение до размера `OVERLAPPED` структуры ( `sizeof(OVERLAPPED)` ).  
  
 Возвращаемое значение E_OUTOFMEMORY указывает, что узлу не удалось инициализировать свои пользовательские данные. В этом случае среда CLR сообщает об ошибке и вызове завершается ошибкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Метод GetHostOverlappedSize](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [Интерфейс IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
