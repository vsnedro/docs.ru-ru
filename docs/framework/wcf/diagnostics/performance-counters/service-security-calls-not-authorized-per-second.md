---
description: 'См. Дополнительные сведения о службе: количество вызовов безопасности, не прошедших авторизацию, в секунду'
title: 'Служба: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 7203b62a1dd2f01aabd8502c992d357742ddc4e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635705"
---
# <a name="service-security-calls-not-authorized-per-second"></a>Служба: количество неавторизованных вызовов системы безопасности в секунду

Имя счетчика: Security Calls Not Authorized Per Second  
  
## <a name="description"></a>Описание  

 Число входящих сообщений в секунду, надлежаще защищенных и поступивших от допустимого пользователя, не авторизованного для выполнения определенных задач.  
  
 Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.  
  
 Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
