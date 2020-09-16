---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 7a3a9bcdb3485efa01ceed61495dd87d64424d50
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550323"
---
# <a name="endpoint-calls-per-second"></a>Конечная точка: количество вызовов в секунду
Имя счетчика: Calls Per Second.  
  
## <a name="description"></a>Описание  
 Количество вызовов данной конечной точки в секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
