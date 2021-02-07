---
description: 'Дополнительные сведения о методе: IHostControl:: SetAppDomainManager'
title: Метод IHostControl::SetAppDomainManager
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: 1fc5efc0afad73d1805338140f186a50913ca542
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708904"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>Метод IHostControl::SetAppDomainManager

Уведомляет узел о том, что домен приложения создан.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwAppDomainID`  
 окне Числовой идентификатор выбранного объекта <xref:System.AppDomain> .  
  
 `pUnkAppDomainManager`  
 окне Указатель на <xref:System.AppDomainManager> объект, который реализуется узлом как `IUnknown` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 <xref:System.AppDomainManager>Предоставляет ведущему приложению механизм для начальной загрузки в управляемый код и управления созданием и параметрами каждого из них <xref:System.AppDomain> . Объект <xref:System.AppDomainManager> загружается в каждый <xref:System.AppDomain> при <xref:System.AppDomain> создании. Если он выбран, среда CLR уведомляет узел о том, что домен приложения был создан, задав значение `pUnkAppDomainManager` параметра.  
  
 В своей реализации `SetAppDomainManager` метода узел может задать имя и тип сборки для диспетчера домена приложения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [Интерфейс IHostControl](ihostcontrol-interface.md)
