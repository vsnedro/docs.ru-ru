---
title: Метод IHostTaskManager::SetUILocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
ms.openlocfilehash: bd1a1d7d2f7f945f345e8af802b881392d6d93e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724225"
---
# <a name="ihosttaskmanagersetuilocale-method"></a>Метод IHostTaskManager::SetUILocale

Уведомляет основное приложение о том, что среда CLR изменила языковой стандарт пользовательского интерфейса (UI), или язык и региональные параметры, в текущей выполняемой задаче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `lcid`  
 окне Значение идентификатора локали, сопоставляемое с новым назначенным географическим языком и региональными параметрами.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetUILocale` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не позволяет управляемому пользовательскому коду изменять язык и региональные параметры пользовательского интерфейса.|  
  
## <a name="remarks"></a>Комментарии  

 Среда выполнения вызывает `SetUILocale` , когда значение <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> свойства изменяется управляемым кодом. Этот метод предоставляет узлу возможность выполнять любые механизмы, которые могут потребоваться для синхронизации языковых стандартов. Если узел не позволяет изменять языковой стандарт пользовательского интерфейса из управляемого кода или не реализует механизм для синхронизации языковых стандартов, он должен возвращать E_NOTIMPL из этого метода.  
  
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
- [Метод SetLocale](ihosttaskmanager-setlocale-method.md)
