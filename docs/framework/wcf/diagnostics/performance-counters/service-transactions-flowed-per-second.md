---
description: 'Дополнительные сведения о службе: количество транзакций, обработанных за секунду'
title: 'Служба: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: aae78853272b46a97ce25a710039661f36bf7079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759501"
---
# <a name="service-transactions-flowed-per-second"></a>Служба: количество поступивших транзакций в секунду

Имя счетчика: Transactions Flowed Per Second.  
  
## <a name="description"></a>Описание  

 Количество транзакций в операциях для данной службы в секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
