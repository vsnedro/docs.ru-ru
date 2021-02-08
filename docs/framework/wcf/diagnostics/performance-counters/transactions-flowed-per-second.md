---
description: 'Дополнительные сведения: количество транзакций в секунду'
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: f37c79e89efb8a013719f44350772919b7222a61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771006"
---
# <a name="transactions-flowed-per-second"></a>Количество поступивших транзакций в секунду

Имя счетчика: Количество поступивших транзакций в секунду  
  
## <a name="description"></a>Описание  

 Количество транзакций в операции в секунду. Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
