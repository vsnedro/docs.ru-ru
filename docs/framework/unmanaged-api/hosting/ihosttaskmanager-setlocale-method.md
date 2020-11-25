---
title: Метод IHostTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: 7730c2dddaca98e4cb06cdb381e8a46ff23c97f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699213"
---
# <a name="ihosttaskmanagersetlocale-method"></a>Метод IHostTaskManager::SetLocale

Уведомляет основное приложение о том, что среда CLR изменила языковой стандарт, или культуру, в текущей выполняемой задаче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `lcid`  
 окне Значение идентификатора локали, сопоставляемое с новым назначенным географическим языком и региональными параметрами.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetLocale` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не позволяет управляемому пользовательскому коду изменять языковой стандарт.|  
  
## <a name="remarks"></a>Комментарии  

 Среда выполнения вызывает `SetLocale` , когда значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> свойства изменяется управляемым кодом. Этот метод предоставляет узлу возможность выполнять любые механизмы, которые могут потребоваться для синхронизации языковых стандартов. Если узел не позволяет изменить языковой стандарт из управляемого кода или не реализует механизм для синхронизации языковых стандартов, он должен возвращать E_NOTIMPL из этого метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Метод SetUILocale](ihosttaskmanager-setuilocale-method.md)
