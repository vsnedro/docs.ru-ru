---
title: Федерация и выданные маркеры
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: dffba51c1bf1aaffbed8725aafc96fd747cb31c6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559256"
---
# <a name="federation-and-issued-tokens"></a>Федерация и выданные маркеры
С помощью Windows Communication Foundation (WCF) можно создавать клиенты, которые безопасно обмениваются данными со службами, реализующими спецификации WS-Federation и WS-Trust. В этих спецификациях XML, протокол SOAP и язык WSDL используются для предоставления механизмов, позволяющих производить проверку подлинности и авторизацию в различных областях доверия.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Федерация](federation.md)  
 Общие сведения о федерации.  
  
 [Федерация и доверие](federation-and-trust.md)  
 Список вопросов архитектуры, о которых необходимо помнить при создании федеративных служб или клиентов.  
  
 [Практическое руководство. Создание федеративного клиента](how-to-create-a-federated-client.md)  
 Основные сведения о создании федеративного клиента с помощью WCF.  
  
 [Практическое руководство. Настройка учетных данных службы федерации](how-to-configure-credentials-on-a-federation-service.md)  
 Основные этапы создания федеративной службы.  
  
 [Практическое руководство. Создание WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)  
 Порядок настройки клиентов и служб, использующих `WSFederationHttpBinding`.  
  
 [Практическое руководство. Создание службы маркеров безопасности](how-to-create-a-security-token-service.md)  
 Этапы создания службы маркеров безопасности.  
  
 [Утверждения и маркеры языка SAML (Security Assertions Markup Language)](saml-tokens-and-claims.md)  
 Маркеры языка Security Assertions Markup Language (SAML), допускающие расширение и позволяющие создавать типы утверждений с широкими функциональными возможностями.  
  
 [Практическое руководство. Настройка локального издателя](how-to-configure-a-local-issuer.md)  
 Порядок создания локального издателя маркеров безопасности.  
  
 [Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Порядок отключения безопасных сеансов в `WSFederationHttpBinding`. Отключение безопасных сеансов необходимо при создании веб-фермы, требующей сеансы для каждого клиента.  
  
## <a name="reference"></a>Справочник  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a>См. также

- [Авторизация](authorization-in-wcf.md)
- [Пользовательские маркеры](../extending/custom-tokens.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
