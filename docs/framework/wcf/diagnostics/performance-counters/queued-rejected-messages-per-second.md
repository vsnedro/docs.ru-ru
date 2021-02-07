---
description: 'Дополнительные сведения о: количество сообщений, отклоненных в очереди, в секунду'
title: Количество сообщений из очереди, отклоненных за секунду
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: d0d227a26a49921449786d2c9f885fac13a82bde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744075"
---
# <a name="queued-rejected-messages-per-second"></a>Количество сообщений из очереди, отклоненных за секунду

Имя счетчика: Queued Messages Rejected Per Second.  
  
## <a name="description"></a>Описание  

 Количество сообщений, отклоненных транспортом очередей этой службы за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
