---
title: Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: 8c2741d7db60781fef12293f3be0b515a55b7885
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705518"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a>Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger

Уведомляет узел о том, что поток, отправляющий этот обратный вызов, будет заблокирован в службах отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a>Remarks  

 `ThreadIsBlockingForDebugger`Метод всегда будет вызываться в потоке среды выполнения.  
  
 `ThreadIsBlockingForDebugger`Метод дает узлу возможность выполнить еще одно действие, пока блокируется поток.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Версии .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)
