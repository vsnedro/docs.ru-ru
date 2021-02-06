---
description: 'Дополнительные сведения: метод ICLRRuntimeInfo:: BindAsLegacyV2Runtime'
title: Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: 77b340cba18ea86546e1a8f4a17933f09289b1de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637186"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime

Привязывает текущую среду выполнения для всех устаревших решений политики активации среды CLR версии 2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие определенные значения HRESULT:  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Либо привязка выполнена успешно, либо эта среда выполнения уже была привязана к устаревшей среде выполнения политики активации CLR версии 2.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.|  
  
## <a name="remarks"></a>Remarks  

 Если текущая среда выполнения уже привязана для всех устаревших решений политики активации CLR версии 2 (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута [ \<startup> элемента](../../configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; вместо этого результат S_OK, как если бы метод успешно привязать политику активации прежних версий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
- [\<startup> Элемент](../../configure-apps/file-schema/startup/startup-element.md)
