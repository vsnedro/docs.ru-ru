---
description: 'Дополнительные сведения: количество вызовов, завершившихся сбоем, в секунду'
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 3961754eb73743a1213922f7c9e1bd164334cd6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759722"
---
# <a name="calls-failed-per-second"></a>Количество сбоев вызовов в секунду

Имя счетчика: Calls Failed Per Second  
  
## <a name="description"></a>Описание  

 Количество вызовов с необработанными исключениями в данной операции в секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Этот счетчик увеличивается каждый раз, когда в этой операции имеется необработанное исключение.  
  
## <a name="see-also"></a>См. также

- [Задание и обработка сбоев в контрактах и службах](../../specifying-and-handling-faults-in-contracts-and-services.md)
