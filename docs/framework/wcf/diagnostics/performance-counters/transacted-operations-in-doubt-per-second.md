---
title: Количество операций с поддержкой транзакций с сомнительным результатом в секунду
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: 9162809ec467f282674e0ab21f7ce5e4d2222da4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249986"
---
# <a name="transacted-operations-in-doubt-per-second"></a>Количество операций с поддержкой транзакций с сомнительным результатом в секунду

Имя счетчика: Количество операций с поддержкой транзакций с сомнительным результатом в секунду.  
  
## <a name="description"></a>Описание  

 Количество операций с поддержкой транзакций, имеющих сомнительный результат, возникающих в данной службе за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
