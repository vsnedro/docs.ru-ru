---
title: Количество сообщений из очереди, отклоненных за секунду
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 2b7686ee94ab051bc255bdb71681c8d1c473094c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276208"
---
# <a name="queued-rejected-messages-per-second"></a>Количество сообщений из очереди, отклоненных за секунду

Имя счетчика: Queued Messages Rejected Per Second.  
  
## <a name="description"></a>Описание  

 Количество сообщений, отклоненных транспортом очередей этой службы за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
