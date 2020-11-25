---
title: Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 443acfa77dc8103008263f19bed116d02e7ea676
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716748"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile

Возвращает данные привязки удостоверения сборки для сборки по указанному пути к файлу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzFilePath`  
 окне Путь к файлу, который необходимо вычислить.  
  
 `dwFlags`  
 окне Значение перечисления [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) , указывающее тип удостоверения сборки. Предоставляется для будущего расширения. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT — единственное значение, поддерживаемое общеязыковой средой выполнения (CLR) версии 2,0.  
  
 `pwzBuffer`  
 заполняет Буфер, содержащий непрозрачные данные идентификации сборки.  
  
 `pcchBufferSize`  
 [вход, выход] Указатель на размер `pwzBuffer` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод возвратился успешно.|  
|E_INVALIDARG|Переданный параметр `pwzFilePath` имеет значение null.|  
|ERROR_INSUFFICIENT_BUFFER|Размер `pwzBuffer` слишком мал.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 `GetBindingIdentityFromFile` обычно вызывается дважды. Первый вызов предоставляет значение NULL для `pwzBuffer` , а метод возвращает соответствующий размер в `pcchBufferSize` . Второй вызов предоставляет соответствующий буфер, а метод возвращает фактические данные буфера после завершения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
