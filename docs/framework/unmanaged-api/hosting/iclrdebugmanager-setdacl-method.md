---
description: 'Дополнительные сведения о методе: ICLRDebugManager:: Сетдакл'
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
ms.openlocfilehash: b507d94f9e23e509d279a0fd4e32c8c996a4668b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689590"
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
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRDebugManager](iclrdebugmanager-interface.md)
- [Метод GetDacl](iclrdebugmanager-getdacl-method.md)
- [Интерфейс IHostControl](ihostcontrol-interface.md)
