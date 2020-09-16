---
title: Аутентификация в WCF
description: Узнайте о некоторых механизмах WCF, обеспечивающих проверку подлинности, таких как проверка подлинности Windows, сертификаты X. 509, а также имя пользователя и пароль.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 414353b360992abea69d47de9efb22c3c77f4bf6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558281"
---
# <a name="authentication-in-wcf"></a>Аутентификация в WCF
В следующих разделах представлен ряд различных механизмов в Windows Communication Foundation (WCF), которые обеспечивают проверку подлинности, например, проверка подлинности Windows, сертификаты X. 509, а также имя пользователя и пароль.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Практическое руководство. Использование поставщика членства ASP.NET](how-to-use-the-aspnet-membership-provider.md)  
 Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации. В этом разделе объясняется, как службы WCF могут использовать одну и ту же базу данных для проверки подлинности и авторизации пользователей.  
  
 [Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля](how-to-use-a-custom-user-name-and-password-validator.md)  
 Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.  
  
 [Идентификация и проверка подлинности службы](service-identity-and-authentication.md)  
 В качестве дополнительной защиты клиент может проверить подлинность службы, указав ожидаемое *удостоверение* службы. Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.  
  
 [Согласование безопасности и тайм-ауты](security-negotiation-and-timeouts.md)  
 Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Отладка ошибок проверки подлинности Windows](debugging-windows-authentication-errors.md)  
 Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.  
  
## <a name="reference"></a>Справочник  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типовые сценарии безопасности](common-security-scenarios.md)  
  
## <a name="see-also"></a>См. также

- [Обзор безопасности](security-overview.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
