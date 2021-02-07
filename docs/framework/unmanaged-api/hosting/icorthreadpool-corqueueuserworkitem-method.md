---
description: 'Дополнительные сведения о методе: ICorThreadpool:: Коркуеуеусерворкитем'
title: Метод ICorThreadpool::CorQueueUserWorkItem
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
ms.openlocfilehash: fc0fc1dc3aa33bf11735fddd2c034af03f269f3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737776"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a>Метод ICorThreadpool::CorQueueUserWorkItem

Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorThreadpool](icorthreadpool-interface.md)
