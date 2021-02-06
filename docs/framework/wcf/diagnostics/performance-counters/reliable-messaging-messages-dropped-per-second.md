---
description: 'Дополнительные сведения о: количество отброшенных сообщений надежных сообщений в секунду'
title: Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 6132316f100cecdba357a6da071e23de8c9a2181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655114"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду

Имя счетчика: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>Описание  

 Общее количество надежных сообщений, которые были отклонены в данной службе в течение секунды.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
