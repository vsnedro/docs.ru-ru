---
description: Дополнительные сведения см. в статье Авторизация в WCF.
title: Авторизация в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 3fda699a33d8b512d047232398e9cfac63661a85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643713"
---
# <a name="authorization-in-wcf"></a>Авторизация в WCF

Авторизация - процесс управления доступом и правами на ресурсы, например службы и файлы. В подразделах этого раздела показано, как выполнить эту базовую задачу в Windows Communication Foundation (WCF) различными способами.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Механизмы управления доступом](access-control-mechanisms.md)  
 Краткий обзор механизмов авторизации в WCF и предлагаемых вариантов использования.  
  
 [Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Показывает процесс ограничения доступа к сервису с помощью класса <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Практическое руководство. Использование поставщика ролей ASP.NET со службой](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Пошаговые инструкции по настройке службы, позволяющие использовать функцию поставщика ролей ASP.NET.  
  
 [Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.NET может использовать диспетчер авторизации для управления авторизацией веб-сайта. WCF также может использовать сочетание ASP.NET/Authorization Manager для авторизации клиентов.  
  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](managing-claims-and-authorization-with-the-identity-model.md)  
 Объясняет основы использования инфраструктуры модели удостоверения для механизма авторизации на основе утверждений.  
  
 [Делегирование и олицетворение](delegation-and-impersonation-with-wcf.md)  
 Объясняет разницу между делегированием и олицетворением.  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Аутентификация](authentication-in-wcf.md)  
  
## <a name="see-also"></a>См. также

- [Обзор безопасности](security-overview.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
