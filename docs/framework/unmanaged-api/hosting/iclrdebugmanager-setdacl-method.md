---
title: Метод ICLRDebugManager::SetDacl
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetDacl
helpviewer_keywords:
- SetDacl method [.NET Framework hosting]
- ICLRDebugManager::SetDacl method [.NET Framework hosting]
ms.assetid: 52f4af3f-e02b-4c20-9fd9-e8e4f4d6fc31
topic_type:
- apiref
ms.openlocfilehash: 66387c686182cb24d8d4d2a445e0e7424d50d5e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615726"
---
# <a name="iclrdebugmanagersetdacl-method"></a>Метод ICLRDebugManager::SetDacl
Этот метод не реализован.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDacl (  
    [in] PACL pacl  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pacl`  
 окне Указатель на список управления доступом (ACL).  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|E_NOTIMPL|Метод не реализован.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRDebugManager](iclrdebugmanager-interface.md)
- [Метод GetDacl](iclrdebugmanager-getdacl-method.md)
- [Интерфейс IHostControl](ihostcontrol-interface.md)
