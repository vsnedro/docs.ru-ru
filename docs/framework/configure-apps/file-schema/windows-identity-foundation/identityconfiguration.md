---
description: 'Дополнительные сведения: <identityConfiguration>'
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 987dfb006984f757ad117157e915f1909ab3a8c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773411"
---
# \<identityConfiguration>

Задает параметры удостоверений уровня службы.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

## <a name="syntax"></a>Синтаксис

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|name|Имя раздела конфигурации удостоверений. Это имя можно использовать для ссылки на конкретный раздел конфигурации. Если `name` атрибут не указан, раздел определяет конфигурацию по умолчанию. Конфигурация по умолчанию всегда используется в сценариях пассивной федерации. Дополнительные сведения см. в описании [\<federationConfiguration>](federationconfiguration.md) элемента.|
|савебутстрапконтекст|Указывает, следует ли включать в маркер сеанса начальные токены. Значение также может быть задано в коллекции обработчиков маркеров путем установки `saveBootstrapContext` атрибута для [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) элемента. Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.|
|максимумклоккскев|Значение типа <xref:System.TimeSpan> , указывающее максимально допустимую отклонение в часах. Управляет максимально разрешенным отклонением по часам при выполнении операций с учетом времени, таких как проверка срока действия сеанса входа. Значение по умолчанию — 5 минут, "00:05:00". Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md). Максимальная разница в часах может также быть задана в коллекции обработчиков маркеров путем установки `maximumClockSkew` атрибута для [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) элемента. Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<caches>](caches.md)|Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров. Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности. Необязательный элемент.|
|[\<certificateValidation>](certificatevalidation.md)|Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов. Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности. Необязательный элемент.|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|Регистрирует диспетчер проверки подлинности утверждений для входящих утверждений. Необязательный элемент.|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|Регистрирует диспетчер авторизации утверждений для входящих утверждений. Необязательный элемент.|
|[\<claimTypeRequired>](claimtyperequired.md)|Указывает набор обязательных утверждений для входящих маркеров безопасности. Необязательный элемент.|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Задает коллекцию обработчиков маркеров безопасности. Можно указать ноль или больше коллекций обработчиков маркеров безопасности. Необязательный элемент.|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Включает обнаружение воспроизведения маркеров и задает срок действия токенов. Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности. Необязательный элемент.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.|

## <a name="remarks"></a>Remarks

Можно определить несколько конфигураций удостоверений, каждый из которых имеет уникальное имя. Поведение выглядит следующим образом:

1. `<identityConfiguration>`Значение, если элемент не указан. Конфигурация удостоверения по умолчанию создается во время выполнения и заполняется значениями по умолчанию.

2. Значение, если `<identityConfiguration>` указан один элемент. Это конфигурация удостоверения по умолчанию. Не имеет значения, является ли он именованным или безымянным.

3. Значение `<identityConfiguration>` , если указано несколько элементов. Неименованный элемент задает конфигурацию удостоверения по умолчанию. Рекомендуется, чтобы при указании нескольких `<identityConfiguration>` элементов одно из них должно быть безымянным.

> [!WARNING]
> Если указать несколько `<identityConfiguration>` элементов, одно из них должно быть безымянным. Неименованный элемент будет конфигурацией удостоверения по умолчанию.

 Некоторые параметры, указанные в элементе, `<identityConfiguration>` могут быть переопределены параметрами в коллекции обработчиков маркеров безопасности или параметрами отдельных обработчиков маркеров безопасности.

> [!IMPORTANT]
> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде конфигурация удостоверения, на которую ссылается элемент, `<federationConfiguration>` настраивает диспетчер авторизации утверждений и политику, которая используется для принятия решений об авторизации. Это справедливо даже в сценариях, которые не являются пассивными веб-сценариями, например Windows Communication Foundation приложений (WCF) или приложение, не основанное на веб-интерфейсе. Если приложение не является пассивным веб-приложением, то [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) к нему применяются только те элементы (и дочерние элемент политики, если таковые имеются) конфигурации удостоверения, на которую указывает ссылка. Все остальные параметры игнорируются. Дополнительные сведения см. в описании [\<federationConfiguration>](federationconfiguration.md) элемента.

`<identityConfiguration>`Элемент представлен <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> классом. Раздел конфигурации Identity представлен <xref:System.IdentityModel.Configuration.IdentityConfiguration> классом.

> [!IMPORTANT]
> Указание следующих элементов в качестве дочерних элементов `<identityConfiguration>` элемента является устаревшим, хотя поведение по-прежнему поддерживается для обеспечения обратной совместимости. Вместо этого эти элементы должны быть указаны в [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) элементе.
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a>Пример

В следующем примере создается конфигурация удостоверения с именем «Алтернатеконфигуратион». Конфигурация удостоверений определяет параметры по умолчанию.

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
