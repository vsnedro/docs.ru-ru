---
title: Метод ICLRRuntimeHost::ExecuteApplication
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
ms.openlocfilehash: 924d032c42dca95b253acea167d55dd6e2b811e5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703334"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>Метод ICLRRuntimeHost::ExecuteApplication
Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене. Дополнительные сведения об этих сценариях см. в разделе [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzAppFullName`  
 окне Полное имя приложения, определенное для <xref:System.ApplicationIdentity> .  
  
 `dwManifestPaths`  
 окне Число строк, содержащихся в `ppwzManifestPaths` массиве.  
  
 `ppwzManifestPaths`  
 [в] Необязательно. Массив строк, содержащий пути манифеста для приложения.  
  
 `dwActivationData`  
 окне Число строк, содержащихся в `ppwzActivationData` массиве.  
  
 `ppwzActivationData`  
 [в] Необязательно. Массив строк, содержащий данные активации приложения, такие как часть строки запроса URL-адреса для приложений, развернутых через Интернет.  
  
 `pReturnValue`  
 заполняет Значение, возвращаемое из точки входа приложения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  
 `ExecuteApplication`используется для активации приложений ClickOnce в только что созданном домене приложения.  
  
 `pReturnValue`Параметру OUTPUT задается значение, возвращаемое приложением. Если для задано значение null, то `pReturnValue` не `ExecuteApplication` завершается ошибкой, но не возвращает значение.  
  
> [!IMPORTANT]
> Не вызывайте метод [метода Start](iclrruntimehost-start-method.md) перед вызовом `ExecuteApplication` метода для активации приложения на основе манифеста. Если `Start` метод вызывается первым, `ExecuteApplication` вызов метода завершится ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [Интерфейс ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Метод SetAppDomainManager](ihostcontrol-setappdomainmanager-method.md)
- [Пошаговое руководство. Загрузка сборок по запросу с помощью API развертывания ClickOnce в конструкторе](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
