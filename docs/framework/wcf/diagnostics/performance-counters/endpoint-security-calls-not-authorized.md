---
description: 'Дополнительные сведения о конечной точке: несанкционированные вызовы безопасности'
title: 'Конечная точка: количество неавторизованных вызовов системы безопасности'
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
ms.openlocfilehash: 258c984e8a7986594b6da6f5c2a8c030907f82ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655478"
---
# <a name="endpoint-security-calls-not-authorized"></a>Конечная точка: количество неавторизованных вызовов системы безопасности

Имя счетчика: Security Calls Not Authorized.  
  
## <a name="description"></a>Описание  

 Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`. Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.
