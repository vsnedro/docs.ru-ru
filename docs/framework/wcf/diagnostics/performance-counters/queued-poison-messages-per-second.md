---
title: Количество подозрительных сообщений из очереди в секунду
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 1e515a81580bd9773841bee4230288d8c7d12216
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276234"
---
# <a name="queued-poison-messages-per-second"></a>Количество подозрительных сообщений из очереди в секунду

Имя счетчика: Queued Poison Messages Per Second.  
  
## <a name="description"></a>Описание  

 Количество сообщений, отмеченных как подозрительные транспортом очередей в этой службе в секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
