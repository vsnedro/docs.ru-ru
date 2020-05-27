---
title: Метод IHostSecurityManager::SetThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: 7891ddc5085eedd2a9010023f119d08f101e2fa3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803779"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a>Метод IHostSecurityManager::SetThreadToken
Задает обработчик для текущего выполняющегося потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hToken`  
 окне Маркер, который задается для выполняемого в данный момент потока.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetThreadToken`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Замечания  
 `IHostSecurityManager::SetThreadToken`ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция Win32 позволяет вызывающему объекту передать маркер произвольному потоку, в то время как он `IHostSecurityManager::SetThreadToken` может связать маркер только с текущим выполняющимся потоком.  
  
 `HANDLE`Тип не совместим с COM, то есть его размер зависит от операционной системы и требует настраиваемого маршалирования. Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Интерфейс IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
