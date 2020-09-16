---
title: Количество удаленных из очереди сообщений в секунду
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: 22b6091693b6a4c8eac9816e8ac15660f4636ec9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552756"
---
# <a name="queue-dropped-messages-per-second"></a>Количество удаленных из очереди сообщений в секунду
Имя счетчика: Queued Messages Dropped Per Second.  
  
## <a name="description"></a>Описание  
 Количество сообщений, отброшенных транспортом очередей этой службы за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
