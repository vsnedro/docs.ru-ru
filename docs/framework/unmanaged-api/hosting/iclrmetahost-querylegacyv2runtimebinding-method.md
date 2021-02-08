---
description: 'Дополнительные сведения о методе: ICLRMetaHost:: QueryLegacyV2RuntimeBinding'
title: Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: ae825c2b2dfe2ce5b75ac9b82511215704fa357f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789857"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding

Возвращает интерфейс, представляющий среду выполнения, к которой привязана политика устаревшей активации, например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута в записи файла конфигурации [ \<startup> элемента](../../configure-apps/file-schema/startup/startup-element.md) , путем непосредственного использования устаревших API-интерфейсов активации или путем вызова метода [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Параметры  

 `riid`  
 окне Обязательно. в настоящее время единственным допустимым значением для этого параметра является `IID_ICLRRuntimeInfo` .  
  
 `ppUnk`  
 [out] Обязательный. При возврате из этого метода содержит указатель на интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , представляющий среду выполнения, привязанную к устаревшей политике активации.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод успешно выполнен, и возвращена среда выполнения, которая была привязана к устаревшей политике активации.|  
|S_FALSE|Метод успешно выполнен, но устаревшая среда выполнения еще не привязана.|  
|E_NOINTERFACE|Метод обнаружил среду выполнения, которая была привязана к устаревшей политике активации, но параметр `riid` не поддерживается этой средой.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](iclrmetahost-interface.md)
- [Размещение](index.md)
