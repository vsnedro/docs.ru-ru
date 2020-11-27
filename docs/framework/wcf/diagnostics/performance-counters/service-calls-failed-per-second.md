---
title: 'Служба: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252976"
---
# <a name="service-calls-failed-per-second"></a>Служба: количество сбоев вызовов в секунду

Имя счетчика: Calls Failed Per Second.  
  
## <a name="description"></a>Описание  

 Число вызовов с необработанными исключениями, получаемых этой службой за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной службе.  
  
## <a name="see-also"></a>См. также

- [Задание и обработка сбоев в контрактах и службах](../../specifying-and-handling-faults-in-contracts-and-services.md)
