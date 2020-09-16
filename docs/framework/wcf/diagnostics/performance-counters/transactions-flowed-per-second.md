---
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: d55856a5d820df2c668863a2a3e853995a113143
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552210"
---
# <a name="transactions-flowed-per-second"></a>Количество поступивших транзакций в секунду
Имя счетчика: Количество поступивших транзакций в секунду  
  
## <a name="description"></a>Описание  
 Количество транзакций в операции в секунду. Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
