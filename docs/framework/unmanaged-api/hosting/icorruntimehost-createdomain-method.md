---
title: Метод ICorRuntimeHost::CreateDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: c495ce47b699d2e32d1f02e4afcf0444a9930c34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723913"
---
# <a name="icorruntimehostcreatedomain-method"></a>Метод ICorRuntimeHost::CreateDomain

Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> на экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType> .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzFriendlyName`  
 окне Необязательный параметр, используемый для присвоения понятного имени домену. Это понятное имя может отображаться в пользовательских интерфейсах, таких как отладчики, для обнаружения домена.  
  
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
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также раздел

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
