---
title: Метод ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: 0557a8f1c7c495950933a44cacd23ada8e84964e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730504"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>Метод ICLRHostProtectionManager::SetProtectedCategories

Указывает, какие категории управляемых типов и членов следует блокировать при выполнении в частично доверенном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `categories`  
 окне Сочетание значений [еапикатегориес](eapicategories-enumeration.md) , указывающих, какие категории управляемых типов и членов должны блокироваться в коде с частичным доверием.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 Каждое `EApiCategories` значение ссылается на список управляемых типов и членов. `EApiCategories`Перечисление и `SetProtectedCategories` метод напрямую связаны с управляемым <xref:System.Security.Permissions.HostProtectionAttribute> классом, который используется для пометки управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описанным в `EApiCategories` . Дополнительные сведения см <xref:System.Security.Permissions.HostProtectionAttribute> . в разделе и <xref:System.Security.Permissions.HostProtectionResource> перечисление, которое непосредственно соответствует `EApiCategories` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [Перечисление EApiCategories](eapicategories-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
