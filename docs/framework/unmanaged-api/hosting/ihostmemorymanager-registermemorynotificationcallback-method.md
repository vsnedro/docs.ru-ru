---
title: Метод IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: edb29378412583d7cdec804b08f8f622d642b02f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731310"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>Метод IHostMemoryManager::RegisterMemoryNotificationCallback

Регистрирует указатель на функцию обратного вызова, которую вызывает хост для уведомления среды CLR о текущей загрузке памяти на компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pCallback`  
 окне Указатель интерфейса на экземпляр [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) , РЕАЛИЗОВАНный средой CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 Поскольку `ICLRMemoryNotificationCallback` интерфейс определяет только один метод ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) и `pCallback` является указателем на `ICLRMemoryNotificationCallback` экземпляр, предоставляемый средой CLR, регистрация фактически осуществляется для самой функции обратного вызова. Узел вызывает `OnMemoryNotification` функцию, чтобы сообщить об условиях нехватки памяти, вместо использования стандартной `CreateMemoryResourceNotification` функции Win32. Дополнительные сведения см. в документации по платформе Windows.  
  
> [!NOTE]
> Вызовы `OnMemoryNotification` никогда не блокируются. Они всегда возвращают немедленно.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md)
- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
