---
description: 'Дополнительные сведения: <wsFederation>'
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: f28c140816dc6de6d618772d5213d6ab094b78c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802129"
---
# \<wsFederation>

Предоставляет конфигурацию для <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederation>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
                  freshness=xs:decimal  
                  homerealm=xs:string (URI)  
                  issuer=xs:string (URI)  
                  persistentCookiesOnPassiveRedirects=xs:boolean  
                  passiveRedirectEnabled=xs:boolean  
                  policy=xs:string (URI)  
                  realm=xs:string (URI)  
                  reply=xs:string (URI)  
                  request=xs:string (URI)  
                  requestPtr=xs:string (URI)  
                  requireHttps=xs:boolean  
                  resource=xs:string (URI)  
                  signInQueryString=xs:string  
                  signOutQueryString=xs:string  
                  signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|authenticationType|Универсальный код ресурса (URI), указывающий тип аутентификации. Задает параметр wauth запроса на вход WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, указывающая, что параметр wauth не включен в запрос.|  
|актуальность|Требуемая максимальная длительность запросов аутентификации в минутах. Задает параметр wfresh запроса входа запроса WS-Federation. Необязательный элемент. По умолчанию используется значение ноль. Необязательный элемент. **Предупреждение:**  В следующем выпуске платформа .NET Framework 4,5 `freshness` атрибут будет иметь тип `xs:string` , а его значение по умолчанию будет `null` .|  
|homeRealm|Домашняя область поставщика удостоверений (IdP), используемая для проверки подлинности. Задает параметр whr запроса входа запроса WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, указывающая, что параметр Втч не включен в запрос.|  
|issuer|Универсальный код ресурса (URI) предполагаемого издателя маркера. Задает базовый URL-адрес WS-Federation запросов на вход в систему и необходимых запросов выхода.|  
|персистенткукиесонпассивередиректс|Указывает, выдаются ли постоянные файлы cookie при проверке подлинности. Необязательный элемент. Значение по умолчанию — false, а файлы cookie не выдаются.|  
|пассивередиректенаблед|Указывает, включена ли ВСФАМ для автоматического перенаправления неавторизованных запросов STS. Необязательный элемент. Значение по умолчанию — true, неавторизованные запросы автоматически перенаправляются.|  
|policy|URL-адрес, указывающий расположение соответствующей политики для использования при запросах на вход. Значение по умолчанию - пустая строка. Задает параметр wp запроса входа запроса WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, которая указывает, что параметр WP не включен в запрос.|  
|realm|Универсальный код ресурса (URI) области запроса. (URI, определяющий проверяющую сторону (RP) для службы маркеров безопасности (STS).) Задает параметр запроса на вход wtrealm WS-Federation. Обязательный элемент.|  
|reply|URL-адрес, указывающий адрес, по которому приложение проверяющей стороны (RP) хотел бы получить ответы от службы токенов безопасности (STS). Задает параметр wreply запроса на вход WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, указывающая, что параметр wreply не включен в запрос.|  
|запрос|Запрос на выдачу маркера. Задает параметр wreq запроса входа запроса WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, указывающая, что параметр wreq не включен в запрос. Не включая wreq или параметр wreqptr в запросе, подразумевает, что STS знает, какой тип маркера следует выдавать.|  
|рекуестптр|URL-адрес, указывающий расположение запроса выдачи токена. Задает параметр запроса wreqptr. Необязательный элемент. Значение по умолчанию — пустая строка, указывающая, что параметр wreqptr не включен в запрос. Не включая wreq или параметр wreqptr в запросе, подразумевает, что STS знает, какой тип маркера следует выдавать.|  
|requireHttps|Указывает, должен ли обмен данными со службой маркеров безопасности (STS) использовать протокол HTTPS. Необязательный элемент. Значение по умолчанию — true, необходимо использовать протокол HTTPS.|  
|resource|Универсальный код ресурса (URI), определяющий ресурс, доступ к которому осуществлялся, проверяющую сторону (RP), для службы токенов безопасности (STS). Необязательный элемент. Задает параметр врес запроса на вход WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, указывающая, что параметр врес не включен в запрос. **Примечание.**  врес является устаревшим параметром. Укажите `realm` атрибут, чтобы использовать вместо него параметр wtrealm.|  
|сигнинкуеристринг|Предоставляет точку расширения для указания параметров запроса, определенных приложением, в WS-Federation URL-адрес запроса на вход. Необязательный элемент. Значение по умолчанию — пустая строка, которая указывает, что в запрос не должны включаться дополнительные параметры. Параметры указываются в виде фрагмента строки запроса в следующей форме: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание.**  В файле конфигурации символ "&" в строке запроса должен быть указан с помощью ссылки на сущность, `&` .|  
|сигнауткуеристринг|Предоставляет точку расширения для указания параметров запроса, определенных приложением, в WS-Federation URL-адрес запроса на вход. Необязательный элемент. Значение по умолчанию — пустая строка, которая указывает, что в запрос не должны включаться дополнительные параметры. Параметры указываются в виде фрагмента строки запроса в следующей форме: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание.**  В файле конфигурации символ "&" в строке запроса должен быть указан с помощью ссылки на сущность, `&` .|  
|сигнаутрепли|Указывает URL-адрес, на который служба маркеров безопасности должна перенаправлять клиент во время пассивного выхода через протокол WS-Federation. Задает параметр wreply для запроса на выход из WS-Federation. Необязательный элемент. Значение по умолчанию — пустая строка, которая указывает, что в запрос не должны включаться дополнительные параметры.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Содержит параметры, которые настраивают свойства <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Remarks  

 Элемент можно использовать `<wsFederation>` для настройки WS-Federation параметров по умолчанию и поведения по умолчанию для всфам. Параметры WS-Federation параметров, определенные в `<wsFederation>` наборе элементов, эквивалентных свойствах, предоставляемых <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> классом. Эти свойства остаются одинаковыми для каждого запроса, выданного ВСФАМ. Параметры WS-Federation можно изменить динамически во время обработки запроса, добавив обработчики событий для событий, предоставляемых ВСФАМ; Например, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> событие. Дополнительные сведения см. в документации по <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> классу.  
  
 `<wsFederation>`Элемент представлен <xref:System.IdentityModel.Services.Configuration.WSFederationElement> классом. Сам объект конфигурации представлен <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> классом. Один <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> экземпляр задается для <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объекта, доступ к которому осуществляется через <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойство и обеспечивает конфигурацию для всфам.  
  
## <a name="example"></a>Пример  

 В следующем XML-коде показан `<wsFederation>` элемент, указывающий параметры для всфам.  
  
> [!WARNING]
> В этом примере ВСФАМ не требуется для использования HTTPS. Это связано с тем, что `requireHttps` атрибут `<wsFederation>` элемента задан `false` . Этот параметр не рекомендуется для большинства рабочих сред, так как может представлять угрозу безопасности.  
  
```xml
<wsFederation passiveRedirectEnabled="true"
              issuer="http://localhost:15839/wsFederationSTS/Issue"
              realm="http://localhost:50969/"
              reply="http://localhost:50969/"
              requireHttps="false"
              signOutReply="http://localhost:50969/SignedOutPage.html"
              signOutQueryString="Param1=value2&Param2=value2"
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
