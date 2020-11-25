---
title: Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
ms.openlocfilehash: 8da9c9fea5cf5b3a27eeb9d0222f0845c832b7da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714202"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy

Изменяет политику привязки для указанной сборки и создает новую версию политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzSourceAssemblyIdentity`  
 окне Идентификатор сборки, которую необходимо изменить.  
  
 `pwzTargetAssemblyIdentity`  
 окне Новое удостоверение измененной сборки.  
  
 `pbApplicationPolicy`  
 окне Указатель на буфер, содержащий данные политики привязки для изменяемой сборки.  
  
 `cbAppPolicySize`  
 окне Размер заменяемой политики привязки.  
  
 `dwPolicyModifyFlags`  
 окне Логическое или сочетание значений [ехостбиндингполицимодифифлагс](ehostbindingpolicymodifyflags-enumeration.md) , указывающее на контроль перенаправления.  
  
 `pbNewApplicationPolicy`  
 заполняет Указатель на буфер, содержащий новые данные политики привязки.  
  
 `pcbNewAppPolicySize`  
 [вход, выход] Указатель на размер нового буфера политики привязки.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Политика успешно изменена.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` или `pwzTargetAssemblyIdentity` является пустой ссылкой.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` слишком мал.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 `ModifyApplicationPolicy`Метод можно вызвать дважды. Первый вызов должен предоставить значение NULL для `pbNewApplicationPolicy` параметра. Этот вызов возвратит с требуемым значением для `pcbNewAppPolicySize` . Второй вызов должен предоставить это значение для `pcbNewAppPolicySize` и указать буфер этого размера для `pbNewApplicationPolicy` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
