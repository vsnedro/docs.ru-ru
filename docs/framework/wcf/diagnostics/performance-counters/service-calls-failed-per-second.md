---
title: 'Служба: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 5629c55cba6f21de24a1de7e8d38a9c08fcf4fb1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559113"
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
