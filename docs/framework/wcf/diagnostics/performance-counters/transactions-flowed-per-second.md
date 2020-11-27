---
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254146"
---
# <a name="transactions-flowed-per-second"></a>Количество поступивших транзакций в секунду

Имя счетчика: Количество поступивших транзакций в секунду  
  
## <a name="description"></a>Описание  

 Количество транзакций в операции в секунду. Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
