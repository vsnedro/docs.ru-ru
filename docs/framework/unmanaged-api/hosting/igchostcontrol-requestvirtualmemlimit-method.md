---
description: 'Дополнительные сведения о методе: Игчостконтрол:: RequestVirtualMemLimit'
title: Метод IGCHostControl::RequestVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: b0ee22671b63be0ed0d23ebb103a6a5a7ca9f2b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709429"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a>Метод IGCHostControl::RequestVirtualMemLimit

Запрашивает у узла изменение ограничений виртуальной памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `sztMaxVirtualMemMB`  
 окне Запрошенный размер выделенной памяти.  
  
 `psztNewMaxVirtualMemMB`  
 [вход, выход] Указатель на фактический размер выделенной памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IGCHostControl](igchostcontrol-interface.md)
