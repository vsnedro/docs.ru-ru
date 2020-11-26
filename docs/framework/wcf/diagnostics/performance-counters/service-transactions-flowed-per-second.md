---
title: 'Служба: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 158bd7e2f2f98e91215ef7351cf90493a2d3059d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236836"
---
# <a name="service-transactions-flowed-per-second"></a>Служба: количество поступивших транзакций в секунду

Имя счетчика: Transactions Flowed Per Second.  
  
## <a name="description"></a>Описание  

 Количество транзакций в операциях для данной службы в секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
