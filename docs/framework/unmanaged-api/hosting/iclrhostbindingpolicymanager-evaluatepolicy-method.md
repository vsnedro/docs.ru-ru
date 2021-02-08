---
description: 'Дополнительные сведения о методе: ICLRHostBindingPolicyManager:: EvaluatePolicy'
title: Метод ICLRHostBindingPolicyManager::EvaluatePolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: e92126a8c12d03ee21e4867754b1a418ef11d463
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789974"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>Метод ICLRHostBindingPolicyManager::EvaluatePolicy

Оценивает политику привязки от имени узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzReferenceIdentity`  
 окне Ссылка на сборку перед вычислением политики.  
  
 `pbApplicationPolicy`  
 окне Указатель на буфер, содержащий данные политики.  
  
 `cbAppPolicySize`  
 окне Размер `pbApplicationPolicy` буфера.  
  
 `pwzPostPolicyReferenceIdentity`  
 заполняет Ссылка на сборку после вычисления новых данных политики.  
  
 `pcchPostPolicyReferenceIdentity`  
 [вход, выход] Указатель на размер буфера ссылки идентификации сборки после вычисления новых данных политики.  
  
 `pdwPoliciesApplied`  
 заполняет Указатель на логическое или сочетание значений [EBindPolicyLevels](ebindpolicylevels-enumeration.md) , указывающих, какие политики были применены.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Оценка успешно завершена.|  
|E_INVALIDARG|Либо `pwzReferenceIdentity` `pbApplicationPolicy` является пустой ссылкой.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` слишком мал.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 `EvaluatePolicy`Метод позволяет основному приложению влиять на политику привязки, чтобы обеспечить соответствие требованиям к версии сборки, относящейся к конкретному узлу. Сам модуль политики остается внутри среды CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
