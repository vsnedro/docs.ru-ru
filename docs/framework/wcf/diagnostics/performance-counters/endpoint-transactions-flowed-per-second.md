---
title: 'Конечная точка: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 9391651eaaca130ef47ddee9daa95b1f8c116892
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553796"
---
# <a name="endpoint-transactions-flowed-per-second"></a>Конечная точка: количество поступивших транзакций в секунду
Имя счетчика: Transactions Flowed Per Second.  
  
## <a name="description"></a>Описание  
 Количество транзакций, поступивших в операции в этой конечной точке в секунду. Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправленном в эту конечную точку, содержится идентификатор транзакции.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
