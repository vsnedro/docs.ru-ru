---
title: Метод ICorRuntimeHost::CreateDomainEx
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
ms.openlocfilehash: d6d9e06b6ed40bb0e5a65fd64f8bca7abe3afa84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715684"
---
# <a name="icorruntimehostcreatedomainex-method"></a>Метод ICorRuntimeHost::CreateDomainEx

Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> в экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType> . Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращаемого <xref:System._AppDomain> экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzFriendlyName`  
 окне Необязательный параметр, используемый для присвоения понятного имени домену. Это понятное имя может отображаться в пользовательских интерфейсах, таких как отладчики, для обнаружения домена.  
  
 `pSetup`  
 окне Необязательный указатель интерфейса типа `IAppDomainSetup` , полученный при вызове метода [ICorRuntimeHost:: креатедомаинсетуп](icorruntimehost-createdomainsetup-method.md) .  
  
 `pIdentityArray`  
 окне Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное через политику безопасности для создания набора разрешений. `IIdentity`Объект можно получить, вызвав метод [креативиденце](icorruntimehost-createevidence-method.md) .  
  
 `pAppDomain`  
 заполняет Указатель интерфейса типа <xref:System._AppDomain> на экземпляр <xref:System.AppDomain?displayProperty=nameWithType> , который может использоваться для дальнейшего управления доменом.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Комментарии  

 `CreateDomainEx` расширяет возможности [CreateDomain](icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передавать `IAppDomainSetup` экземпляр со значениями свойств для настройки домена приложения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Версия .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также раздел

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Метод CreateDomain](icorruntimehost-createdomain-method.md)
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
