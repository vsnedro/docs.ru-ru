---
description: 'Дополнительные сведения о методе: IGCHost:: Сетгкстартуплимитс'
title: Метод IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 91c74d54189bbfb7e9f208e507fe6e75b7023e00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709507"
---
# <a name="igchostsetgcstartuplimits-method"></a>Метод IGCHost::SetGCStartupLimits

Задает размер сегмента и максимальный размер для поколения 0.  
  
> [!IMPORTANT]
> Начиная с платформа .NET Framework 4,5 можно задать размер сегмента и максимальный размер поколения 0 в значениях, превышающих `DWORD` использование метода [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `SegmentSize`  
 окне Размер сегмента, используемого системой сборки мусора.  
  
 `MaxGen0Size`  
 окне Максимальный размер для поколения 0.  
  
## <a name="remarks"></a>Remarks  

 `SetGCStartupLimits`Метод может быть вызван только один раз. Эти значения нельзя изменить позже.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IGCHost](igchost-interface.md)
