---
title: Метод IGCHost2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
ms.openlocfilehash: ca9566168b8aae361af8d61539066624697a2d04
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805147"
---
# <a name="igchost2setgcstartuplimitsex-method"></a>Метод IGCHost2::SetGCStartupLimitsEx
Задает размер сегмента и максимальный размер для поколения 0.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `SegmentSize`  
 окне Размер сегмента, используемого системой сборки мусора.  
  
 `MaxGen0Size`  
 окне Максимальный размер для поколения 0.  
  
## <a name="remarks"></a>Замечания  
 Значения, которые `SetGCStartupLimitsEx` задаются, можно указать только перед запуском узла. Эти значения нельзя изменить позже.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IGCHost2](igchost2-interface.md)
