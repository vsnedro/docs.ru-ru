---
description: 'Дополнительные сведения о методе: IGCHost2:: SetGCStartupLimitsEx'
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
ms.openlocfilehash: 32d3bcbb467a1a418c7123779c881c46e983edef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709312"
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
  
## <a name="remarks"></a>Remarks  

 Значения, которые `SetGCStartupLimitsEx` задаются, можно указать только перед запуском узла. Эти значения нельзя изменить позже.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IGCHost2](igchost2-interface.md)
