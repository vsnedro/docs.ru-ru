---
title: Утверждения и маркеры SAML
description: Узнайте, как WFC использует маркеры SAML для выполнения инструкций, которые являются наборами утверждений, сделанных одной сущностью для другой сущности.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
ms.openlocfilehash: a1de58ae28041b8e89822120c9369612217eb3b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288520"
---
# <a name="saml-tokens-and-claims"></a>Утверждения и маркеры SAML

*Маркеры* безопасности (SAML) — это XML-представления утверждений. По умолчанию маркеры SAML Windows Communication Foundation (WCF) используются в сценариях федеративной безопасности — это *выдается токены*.  
  
 Маркеры SAML содержат операторы, которые являются набором утверждений, выполненных одной сущностью в отношении другой сущности. Например, в сценариях федеративной безопасности операторы относительно пользователя выполняются в системе службой маркеров безопасности. Служба маркеров безопасности подписывает маркер SAML, чтобы подтвердить достоверность оператора, содержащегося в маркере. Кроме того, маркер SAML связан с материалом ключа шифрования, который должен быть известен пользователю маркера SAML. Эта проверка убеждает проверяющую сторону, что на самом деле маркер SAML был выдан указанному пользователю. Например, в типичном сценарии происходит следующее.  
  
1. Клиент запрашивает маркер SAML у службы маркеров безопасности, проходя проверку подлинности в службе маркеров безопасности с использованием учетных данных Windows.  
  
2. Служба маркеров безопасности выдает маркер SAML клиенту. Маркер SAML подписан сертификатом, связанным со службой маркеров безопасности, и содержит ключ проверки, зашифрованный для целевой службы.  
  
3. Клиент также получает копию *ключа подтверждения*. Затем клиент представляет токен SAML для службы приложения ( *проверяющей* стороны) и подписывает сообщение с помощью ключа подтверждения.  
  
4. Подпись маркера SAML указывает проверяющей стороне, что маркер выдан службой маркеров безопасности. Подпись сообщения, созданная при помощи ключа проверки, указывает проверяющей стороне, что маркер был выдан клиенту.  
  
## <a name="from-claims-to-samlattributes"></a>От Claims к SamlAttributes  

 В WCF инструкции в маркерах SAML моделируются как <xref:System.IdentityModel.Tokens.SamlAttribute> объекты, которые могут быть заполнены непосредственно из <xref:System.IdentityModel.Claims.Claim> объектов, если <xref:System.IdentityModel.Claims.Claim> объект имеет <xref:System.IdentityModel.Claims.Claim.Right%2A> свойство класса <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> и <xref:System.IdentityModel.Claims.Claim.Resource%2A> свойство имеет тип <xref:System.String> . Пример:  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
> Если в сообщениях маркеры SAML сериализуются, выдаются они службой маркеров безопасности или предоставляются клиентами службам как часть проверки подлинности, максимальный размер квоты сообщения должен быть достаточно большим, чтобы вместить маркер SAML и другие части сообщения. Как правило, по умолчанию квоты на размер сообщения являются достаточными. Впрочем, в случае большого размера маркера SAML (когда он содержит сотни утверждений), может потребоваться увеличение квот для выделения места сериализованному маркеру. Дополнительные сведения см. в разделе [вопросы безопасности данных](security-considerations-for-data.md).  
  
## <a name="from-samlattributes-to-claims"></a>От SamlAttributes к Claims  

 Различные операторы в маркере SAML преобразуются в объекты <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, которые помещаются в класс <xref:System.IdentityModel.Policy.AuthorizationContext>, когда в сообщении содержатся маркеры SAML. Утверждения от каждого оператора SAML возвращаются свойством <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> класса <xref:System.IdentityModel.Policy.AuthorizationContext> и могут быть проверены на необходимость проверки подлинности и авторизации пользователя.  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [Федерация](federation.md)
- [Практическое руководство. Создание федеративного клиента](how-to-create-a-federated-client.md)
- [Практическое руководство. Настройка учетных данных службы федерации](how-to-configure-credentials-on-a-federation-service.md)
- [Управление утверждениями и авторизацией с помощью модели удостоверения](managing-claims-and-authorization-with-the-identity-model.md)
- [Утверждения и маркеры](claims-and-tokens.md)
- [Создание утверждений и значения ресурсов](claim-creation-and-resource-values.md)
- [Практическое руководство. Создание пользовательского утверждения](../extending/how-to-create-a-custom-claim.md)
