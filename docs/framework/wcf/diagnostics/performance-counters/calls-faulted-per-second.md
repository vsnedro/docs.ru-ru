---
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: a50d1881040f248d7c58e82ce2e477b51591c2f3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553588"
---
# <a name="calls-faulted-per-second"></a>Количество сбоев вызовов в секунду
Имя счетчика: Calls Faulted Per Second  
  
## <a name="description"></a>Описание  
 Число вызовов, возвращающих ошибки этой операции за секунду.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 В приложениях Windows Communication Foundation (WCF) методы служб обмениваются сведениями об ошибках обработки с помощью сообщений о сбоях SOAP. Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы. Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.  
  
## <a name="see-also"></a>См. также

- [Задание и обработка сбоев в контрактах и службах](../../specifying-and-handling-faults-in-contracts-and-services.md)
