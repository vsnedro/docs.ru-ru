---
title: Расширение безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: d91f4812dbccb7807be2e0780cccd1d0c38b1f40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273065"
---
# <a name="extending-security"></a>Расширение безопасности

Для поддержки новых типов утверждений и пользовательских маркеров можно расширить инфраструктуру безопасности Windows Communication Foundation (WCF). Это подробно описывается в следующих подразделах.  
  
## <a name="in-this-section"></a>в этом разделе  
  
 [Пользовательские учетные данные и проверка учетных данных](custom-credential-and-credential-validation.md)  
 Рассматривается, как модель удостоверения используется при проверке пользовательских учетных данных.  
  
 [Пользовательские маркеры](custom-tokens.md)  
 Маркеры, выдаваемые службой маркеров безопасности (STS), - обычно маркеры SAML. В этом разделе описывается, как создать тип пользовательского маркера.  
  
 [Пользовательская авторизация](custom-authorization.md)  
 Объясняется, как реализовать пользовательскую авторизацию.  
  
 [Переопределение идентификатора службы для проверки подлинности](overriding-the-identity-of-a-service-for-authentication.md)  
 Описывается, как переопределить идентификацию службы для проверки подлинности.  
  
 [Практическое руководство. Создание пользовательского средства проверки идентификации клиентов](how-to-create-a-custom-client-identity-verifier.md)  
 Демонстрирует, как проверить идентификацию пользовательской конечной точки.  
  
 [Практическое руководство. Использование отдельных сертификатов X.509 для подписывания и шифрования](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Обычно сообщения подписываются и шифруются одним сертификатом. В этом разделе объясняется, как при необходимости использовать два сертификата.  
  
 [Практическое руководство. Изменение поставщика служб шифрования для закрытого ключа сертификата X.509](change-cryptographic-provider-x509-certificate-private-key.md)  
 Объясняет, как изменить поставщик служб шифрования, используемый для предоставления закрытого ключа сертификата X. 509, и как интегрировать поставщик в платформу Windows Communication Foundation (WCF).  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Безопасность](../feature-details/security.md)  
  
 [Базовое программирование для WCF](../basic-wcf-programming.md)  
  
## <a name="see-also"></a>См. также

- [Обзор безопасности](../feature-details/security-overview.md)
