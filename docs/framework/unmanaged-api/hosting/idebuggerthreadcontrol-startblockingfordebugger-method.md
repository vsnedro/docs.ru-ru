---
title: Метод IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 1e0cb52a6b9f03209256e5398415b4ec632fb5e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705512"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a>Метод IDebuggerThreadControl::StartBlockingForDebugger

Уведомляет узел о том, что служба отладки собирается начать блокирование всех потоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwUnused`  
 [in] Зарезервирован для будущего использования.  
  
## <a name="remarks"></a>Комментарии  

 `StartBlockingForDebugger`Метод может быть вызван в потоке среды выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)
