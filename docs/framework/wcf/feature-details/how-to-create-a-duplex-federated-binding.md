---
description: Дополнительные сведения см. в статье как создать дуплексную федеративный привязку
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 92d5eeeffab88d88aa245b51738048dced2d5d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779911"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Практическое руководство. Создание дуплексной федеративной привязки

Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос-ответ». Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку. В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP. Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.

Также можно создать привязку в коде. Описание создаваемого стека элементов привязки см. в разделе [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Создание дуплексной федеративной пользовательской привязки с использованием HTTP

1. В [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) узле файла конфигурации создайте [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) элемент.

2. Внутри [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) элемента создайте [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемент с `name` атрибутом, для которого задано значение `FederationDuplexHttpMessageSecurityBinding` .

3. Внутри [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемента создайте [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибутом, для которого задано значение `SecureConversation` .

4. Внутри [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемента создайте элемент, атрибут которого имеет [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` значение `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated` .

5. После [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемента создайте пустой [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) элемент.

6. После [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) элемента создайте пустой [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) элемент.

7. После [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) элемента создайте пустой [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) элемент.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP

1. В [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) узле файла конфигурации создайте [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) элемент.

2. Внутри [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) элемента создайте [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемент с `name` атрибутом, для которого задано значение `FederationDuplexTcpMessageSecurityBinding` .

3. Внутри [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемента создайте [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибутом, для которого задано значение `SecureConversation` .

4. Внутри [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемента создайте элемент, атрибут которого имеет [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` значение `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated` .

5. После [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемента создайте пустой [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) элемент.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP

1. В [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) узле файла конфигурации создайте [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) элемент.

2. Внутри [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) элемента создайте [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемент с `name` атрибутом, для которого задано значение `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .

3. Внутри [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемента создайте [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибутом, для которого задано значение `SecureConversation` .

4. Внутри [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемента создайте элемент, атрибут которого имеет [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` значение `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated` .

5. После [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) элемента создайте пустой [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) элемент.

6. После [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) элемента создайте пустой [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) элемент.

## <a name="code-sample"></a>Образец кода

### <a name="sample-with-3-bindings"></a>Образец с 3 привязками

1. Вставьте следующий код в свой файл конфигурации.

## <a name="example"></a>Пример

```xml
<bindings>
   <customBinding>
      <binding name="FederationDuplexHttpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <compositeDuplex />
          <oneWay />
          <httpTransport />
       </binding>
<!-- duplex over https is not supported -->
       <binding name="FederationDuplexTcpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <tcpTransport />
       </binding>
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />
          </security>
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->
          <sslStreamSecurity />
          <tcpTransport />
       </binding>
    </customBinding>
</bindings>
```
