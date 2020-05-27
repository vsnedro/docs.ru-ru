---
title: Интерфейс IDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805279"
---
# <a name="idebuggerthreadcontrol-interface"></a>Интерфейс IDebuggerThreadControl
Предоставляет методы для уведомления узла о блокировке и разблокировке потоков службами отладки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ThreadIsBlockingForDebugger](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|Уведомляет узел о том, что поток, отправляющий этот обратный вызов, будет заблокирован в службах отладки.|  
|[Метод ReleaseAllRuntimeThreads](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|Уведомляет узел о том, что службы отладки собирается освободить все заблокированные потоки.|  
|[Метод StartBlockingForDebugger](idebuggerthreadcontrol-startblockingfordebugger-method.md)|Уведомляет узел о том, что служба отладки собирается начать блокирование всех потоков.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейсы размещения](hosting-interfaces.md)
