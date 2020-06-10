---
title: Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 600b9c28d92f9e2b6e4d586b052cc5762d591521
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599065"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0

Службы Windows Communication Foundation (WCF) являются совместимыми с расширениями веб-служб 3,0 для клиентов Microsoft .NET (WSE), если службы WCF настроены для использования версии WS-Addressing в августе 2004.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Включение службы WCF для взаимодействия с клиентами WSE 3.0

1. Определите пользовательскую привязку для службы WCF.

    Чтобы указать, что для кодирования сообщений используется версия спецификации WS-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.

    1. Добавьте дочерний элемент в [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) файл конфигурации службы.

    2. Укажите имя привязки, добавив в [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) и установив `name` атрибут.

    3. Укажите режим проверки подлинности и версию спецификаций WS-Security, которые используются для защиты сообщений, совместимых с WSE 3,0, добавив дочерний элемент [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) в [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .

        Чтобы задать режим проверки подлинности, задайте `authenticationMode` атрибут [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) . Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0. Следующая таблица сопоставляет режимы проверки подлинности в WCF с готовыми утверждениями безопасности в WSE 3,0.

        |Режим проверки подлинности WCF|Готовое к использованию утверждение безопасности WSE 3.0|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \*Одно из основных различий между `mutualCertificate10Security` `mutualCertificate11Security` утвержденными утверждениями безопасности и является версией спецификации WS-Security, которую WSE использует для защиты сообщений SOAP. Для `mutualCertificate10Security` используется версия WS-Security 1.0, а для `mutualCertificate11Security` - версия WS-Security 1.1. Для WCF версия спецификации WS-Security указывается в `messageSecurityVersion` атрибуте [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .

        Чтобы задать версию спецификации WS-Security, используемую для защиты сообщений SOAP, установите `messageSecurityVersion` атрибут [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) . Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.

    4. Укажите, что в WCF используется версия спецификации WS-Addressing 2004 августа, добавив [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) и присвойте свойству `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> .

        > [!NOTE]
        > При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.

2. Укажите, что служба использует пользовательскую привязку.

    1. Присвойте `binding` атрибуту [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) элемента значение `customBinding` .

    2. Присвойте `bindingConfiguration` атрибуту [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) элемента значение, указанное в `name` атрибуте объекта [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) для пользовательской привязки.

## <a name="example"></a>Пример

Следующий пример кода задает, что служба `Service.HelloWorldService` использует для взаимодействия с клиентами WSE 3.0 пользовательскую привязку. Пользовательская привязка задает, что для кодирования пересылаемых сообщений используется версия спецификация WS-Addressing от августа 2004 г. и набор спецификаций WS-Security 1.1. Защита сообщений обеспечивается с помощью режима проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.

```xml
<configuration>
  <system.serviceModel>
    <services>
      <service
        behaviorConfiguration="ServiceBehavior"
        name="Service.HelloWorldService">
        <endpoint binding="customBinding" address=""
          bindingConfiguration="ServiceBinding"
          contract="Service.IHelloWorld"></endpoint>
      </service>
    </services>

    <bindings>
      <customBinding>
        <binding name="ServiceBinding">
          <security authenticationMode="AnonymousForCertificate"
                  messageProtectionOrder="SignBeforeEncrypt"
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"
                  requireDerivedKeys="false">
          </security>
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>
          <httpTransport/>
        </binding>
      </customBinding>
    </bindings>
    <behaviors>
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">
        <serviceCredentials>
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>
        </serviceCredentials>
      </behavior>
    </behaviors>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Дополнительно

- [Практическое руководство. Изменение привязки, предоставляемой системой](../extending/how-to-customize-a-system-provided-binding.md)
