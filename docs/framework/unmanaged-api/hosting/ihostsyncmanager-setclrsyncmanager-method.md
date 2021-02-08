---
description: 'Дополнительные сведения о методе: метод ihostsyncmanager:: Сетклрсинкманажер'
title: Метод IHostSyncManager::SetCLRSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
ms.openlocfilehash: e2a6a54334f7b8a63696ead918f4f34e0c36e438
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784721"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a>Метод IHostSyncManager::SetCLRSyncManager

Задает экземпляр [ICLRSyncManager](iclrsyncmanager-interface.md) , связываемый с текущим экземпляром [метод ihostsyncmanager](ihostsyncmanager-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pManager`  
 окне Указатель на `ICLRSyncManager` экземпляр, предоставленный средой CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetCLRSyncManager` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Для упрощения обмена данными между узлом и средой CLR интерфейсы размещения обычно бывают парными. Один член пары реализуется узлом, а другой — средой CLR. В качестве реализации на стороне узла `IHostSyncManager` интерфейс соответствует `ICLRSyncManager` интерфейсу, РЕАЛИЗОВАНному средой CLR. Среда CLR вызывает метод, `SetCLRSyncManager` чтобы предоставить `ICLRSyncManager` узлу экземпляр, связываемый с текущим `IHostSyncManager` экземпляром.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
