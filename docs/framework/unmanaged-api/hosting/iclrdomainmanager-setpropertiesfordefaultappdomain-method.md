---
description: 'Дополнительные сведения о методе: Иклрдомаинманажер:: Сетпропертиесфордефаултаппдомаин'
title: Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 08e6c885d5d089fa22c30a4e3cef69480b840031
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689447"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain

Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `nProperties`  
 окне Число записей в `pwszPropertyNames` и `pwszPropertyValues` .  
  
 `pwszPropertyNames`  
 окне Массив имен свойств или значение null, если свойства отсутствуют. В настоящее время единственным именем свойства, распознаваемым этим методом, является "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 окне Массив значений свойств или значение null, если свойства отсутствуют.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` содержит имя свойства, которое не распознается этим методом.|  
  
## <a name="remarks"></a>Remarks  

 Значение свойства для "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" — это список сборок, имеющих условный <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA) с <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> флагом, который должен быть видимым для частично доверенных вызывающих объектов в домене приложения по умолчанию.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение](index.md)
- [Интерфейс ICLRDomainManager](iclrdomainmanager-interface.md)
