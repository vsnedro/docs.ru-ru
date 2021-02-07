---
description: 'Дополнительные сведения: количество отправленных сообщений из очереди в секунду'
title: Количество удаленных из очереди сообщений в секунду
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: e5959b76795514dec03d6ae4d08ac248994777fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759553"
---
# <a name="queue-dropped-messages-per-second"></a>Количество удаленных из очереди сообщений в секунду

Имя счетчика: Queued Messages Dropped Per Second.  
  
## <a name="description"></a>Описание  

 Количество сообщений, отброшенных транспортом очередей этой службы за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
