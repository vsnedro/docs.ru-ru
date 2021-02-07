---
description: 'Дополнительные сведения о: <issuerChannelBehaviors> element'
title: Элемент <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: 6be79f2ee6afb442a7a399ce49df4ad59dff2db5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725549"
---
# <a name="issuerchannelbehaviors-element"></a>\::: No-Loc ( <issuerChannelBehaviors> )::: элемент

Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) (определенную в конфигурации) для использования при взаимодействии с указанными службами маркеров службы. Определенные поведения не могут содержать элементы [ \: :: No-Loc ( <clientCredentials> ):::](clientcredentials.md) .

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\::: No-Loc (<System. serviceModel>):::](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\::: No-Loc ( <behaviors> ):::](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: No-Loc ( <endpointBehaviors> ):::](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: No-Loc ( <behavior> ):::](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: No-Loc ( <clientCredentials> ):::](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: No-Loc ( <issuedToken> ):::](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\::: No-Loc ( <issuerChannelBehaviors> ):::

## <a name="syntax"></a>Синтаксис

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|Добавляет поведение в коллекцию.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\::: No-Loc ( <issuedToken> ):::](issuedtoken.md)|Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.|

## <a name="remarks"></a>Remarks

Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`). Например, если необходимо добавить элемент [ \: :: No-Loc ( <dataContractSerializer> ):::](datacontractserializer-element.md) Behavior.

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Идентификация и проверка подлинности службы](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Поведение безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Обеспечение безопасности клиентов](../../../wcf/securing-clients.md)
- [Практическое руководство. Создание федеративного клиента](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Практическое руководство. Настройка локального издателя](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
