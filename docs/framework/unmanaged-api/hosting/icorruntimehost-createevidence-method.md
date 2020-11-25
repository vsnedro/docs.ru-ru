---
title: Метод ICorRuntimeHost::CreateEvidence
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 6627fce519934177aefd26a612e5b00ca1941d02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715671"
---
# <a name="icorruntimehostcreateevidence-method"></a>Метод ICorRuntimeHost::CreateEvidence

Возвращает указатель интерфейса типа <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> , который позволяет основному приложению создавать доказательства безопасности для передачи в метод [CreateDomain](icorruntimehost-createdomain-method.md) или [CreateDomainEx](icorruntimehost-createdomainex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pEvidence`  
 заполняет Указатель интерфейса на экземпляр, <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> используемый для создания свидетельств безопасности. Этот указатель типизирован `IUnknown` , поэтому вызывающие объекты обычно должны вызывать `QueryInterface` этот интерфейс для получения указателя на <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Комментарии  

 Этот метод возвращает пустую коллекцию, которая не может быть заполнена из машинного кода. Вместо этого следует использовать <xref:System.Security.Policy.Evidence> метод.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Версия .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также раздел

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
