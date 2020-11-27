---
title: 'Конечная точка: количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду'
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: b9aa0e62aaf3a7e44f90c37a8611733321969ded
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290833"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a>Конечная точка: количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду

Имя счетчика: Reliable Messaging Sessions Faulted Per Second.  
  
## <a name="description"></a>Описание  

 Количество сеансов надежного обмена сообщениями, в которых произошел сбой на этой конечной точке в течение секунды.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
