---
description: 'Дополнительные сведения о методе: Идебугжерсреадконтрол:: StartBlockingForDebugger'
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
ms.openlocfilehash: 3e19817c4adbefd1dd70be047656b3fea261c389
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709683"
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
  
## <a name="remarks"></a>Remarks  

 `StartBlockingForDebugger`Метод может быть вызван в потоке среды выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)
