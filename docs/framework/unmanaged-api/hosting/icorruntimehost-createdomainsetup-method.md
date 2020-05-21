---
title: Метод ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: aa1ce70311cd4ef0204c1c31efee8bd7b313c81d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762335"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a>Метод ICorRuntimeHost::CreateDomainSetup
Возвращает указатель интерфейса типа IAppDomainSetup на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляр. `IAppDomainSetup`предоставляет методы для настройки аспектов домена приложения перед его созданием.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomainSetup`  
 заполняет Указатель интерфейса на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляр. Этот параметр типизирован как `IUnknown` , поэтому вызывающие объекты должны обычно вызывать `QueryInterface` этот указатель для получения указателя интерфейса типа `IAppDomainSetup` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Комментарии  
 Указатель, возвращаемый из этого метода, обычно передается в качестве параметра в метод [CreateDomainEx](icorruntimehost-createdomainex-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версия .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
