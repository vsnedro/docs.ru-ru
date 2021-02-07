---
description: 'Дополнительные сведения: число вызовов в секунду'
title: Количество вызовов в секунду
ms.date: 03/30/2017
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
ms.openlocfilehash: 1d204e4c88d9f9ab113e59c76f1eaecc280e552e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759657"
---
# <a name="calls-per-second"></a>Количество вызовов в секунду

Имя счетчика: Calls Per Second  
  
## <a name="description"></a>Описание  

 Число вызовов данной операции в секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
