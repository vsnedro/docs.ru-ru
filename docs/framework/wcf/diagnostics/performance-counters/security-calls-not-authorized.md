---
description: 'Дополнительные сведения: несанкционированные вызовы безопасности'
title: Неавторизованные вызовы системы безопасности
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
ms.openlocfilehash: 80dc161f2be5a678e80860410f1b6adbde7bfb71
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803416"
---
# <a name="security-calls-not-authorized"></a>Неавторизованные вызовы системы безопасности

Имя счетчика: Security Calls Not Authorized.  
  
## <a name="description"></a>Описание  

 Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`. Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.
