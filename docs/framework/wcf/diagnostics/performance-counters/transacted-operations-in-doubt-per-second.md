---
title: Количество операций с поддержкой транзакций с сомнительным результатом в секунду
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: 59186b1fc113bb87264a8b946cfee2719ff50b62
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550603"
---
# <a name="transacted-operations-in-doubt-per-second"></a>Количество операций с поддержкой транзакций с сомнительным результатом в секунду
Имя счетчика: Количество операций с поддержкой транзакций с сомнительным результатом в секунду.  
  
## <a name="description"></a>Описание  
 Количество операций с поддержкой транзакций, имеющих сомнительный результат, возникающих в данной службе за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
