---
description: 'Дополнительные сведения: количество прерванных операций транзакций в секунду'
title: Количество прерванных операций с поддержкой транзакций в секунду
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: de130c18e065e48ed7ac18442b2bc5f82c2f6861
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771201"
---
# <a name="transacted-operations-aborted-per-second"></a>Количество прерванных операций с поддержкой транзакций в секунду

Имя счетчика: Количество прерванных операций с поддержкой транзакций в секунду.  
  
## <a name="description"></a>Описание  

 Количество транзакционных операций, прерванных в этой службе за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
