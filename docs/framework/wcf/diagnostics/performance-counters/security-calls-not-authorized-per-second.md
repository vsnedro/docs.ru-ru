---
title: Количество неавторизованных вызовов системы безопасности в секунду
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 1e1e58946783c2eb376ae6ba50c3595c037a1e00
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276117"
---
# <a name="security-calls-not-authorized-per-second"></a>Количество неавторизованных вызовов системы безопасности в секунду

Имя счетчика: Security Calls Not Authorized Per Second.  
  
## <a name="description"></a>Описание  

 Число вызовов, которые не удалось авторизовать в данной операции, в секунду.  
  
 Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`. Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
