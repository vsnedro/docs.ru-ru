---
title: Практическое руководство. Задание значений учетных данных клиента
description: Узнайте, как служба WCF может указать, как клиент проходит проверку подлинности в этой службе. В этом примере указывается сертификат X. 509 и транспортный режим.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 75a21a7dc083282f6b2fe839167ff1b2eddfb373
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244456"
---
# <a name="how-to-specify-client-credential-values"></a>Практическое руководство. Задание значений учетных данных клиента

С помощью Windows Communication Foundation (WCF) служба может указать, как клиент проходит проверку подлинности в службе. Например, в службе можно указать, что клиент проходит проверку подлинности с помощью сертификата.

## <a name="to-determine-the-client-credential-type"></a>Определение типа учетных данных клиента

1. Получите метаданные из конечной точки метаданных службы. Метаданные обычно состоят из двух файлов: код клиента на выбранном языке программирования (по умолчанию - Visual C#) и XML-файл конфигурации. Одним из способов получения метаданных является использование программы Svcutil.exe для возвращения кода клиента и конфигурации клиента. Дополнительные сведения см. в разделе [Получение метаданных](./feature-details/retrieving-metadata.md) и [служебная программа метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).

2. Откройте XML-файл конфигурации. Если используется программа Svcutil.exe, то по умолчанию файл имеет имя Output.config.

3. Найдите **\<security>** элемент с помощью атрибута **mode** ( **\<security mode =**`MessageOrTransport`**>** где `MessageOrTransport` задается один из режимов безопасности.

4. Найдите дочерний элемент, соответствующий значению режима. Например, если для режима задано значение **Message**, найдите элемент, **\<message>** содержащийся в **\<security>** элементе.

5. Запишите значение, присвоенное атрибуту **ClientCredentialType** . Фактическое значение зависит от используемого режима - транспорт или сообщение.

Следующий XML-код представляет конфигурацию для клиента, использующего безопасность сообщений. Для проверки подлинности клиента требуется сертификат.

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Пример: транспортный режим TCP с сертификатом в качестве учетных данных клиента

В этом примере в качестве режима безопасности задается Transport, а в качестве значения учетных данных клиента - сертификат X.509. В следующих процедурах показано, как задать значение учетных данных клиента в коде клиента и в конфигурации. Предполагается, что вы использовали [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для возврата метаданных (кода и конфигурации) из службы. Дополнительные сведения см. [в разделе инструкции. Создание клиента](how-to-create-a-wcf-client.md).

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>Указание значения учетных данных клиента в коде клиента

1. Используйте [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания кода и конфигурации из службы.

2. Создайте экземпляр клиента WCF с помощью созданного кода.

3. В классе клиента задайте соответствующее значение для свойства <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>. В этом примере в качестве значения свойства задается сертификат X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     Можно использовать любое перечисление класса <xref:System.Security.Cryptography.X509Certificates.X509FindType>. В случае, если сертификат изменен (в связи с истечением срока действия) используется имя субъекта. Использование имени субъекта позволяет инфраструктуре снова найти сертификат.

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>Указание значения учетных данных клиента в конфигурации клиента

1. Добавьте [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент в [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) элемент.

2. Добавьте [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) элемент в [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) элемент. Необходимо присвоить обязательному атрибуту `name` соответствующее значение.

3. Добавьте [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) элемент в [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) элемент.

4. Присвойте соответствующие значения следующим атрибутам: `storeLocation`, `storeName`, `x509FindType` и `findValue`, как показано в следующем коде. Дополнительные сведения см. в разделе [Работа с сертификатами](./feature-details/working-with-certificates.md).

    ```xml
    <behaviors>
       <endpointBehaviors>
          <behavior name="endpointCredentialBehavior">
            <clientCredentials>
              <clientCertificate findValue="Contoso.com"
                                 storeLocation="LocalMachine"
                                 storeName="TrustedPeople"
                                 x509FindType="FindBySubjectName" />
            </clientCredentials>
          </behavior>
       </endpointBehaviors>
    </behaviors>
    ```

5. При настройке клиента укажите поведение, задав атрибут `behaviorConfiguration` элемента `<endpoint>`, как показано в следующем коде. Элемент конечной точки является дочерним по отношению к [\<client>](../configure-apps/file-schema/wcf/client.md) элементу. Также укажите имя конфигурации привязки, установив привязку для клиента в атрибуте `bindingConfiguration`. Если используется созданный файл конфигурации, имя привязки создается автоматически. В этом примере используется имя `"tcpBindingWithCredential"`.

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Программирование безопасности WCF](./feature-details/programming-wcf-security.md)
- [Выбор типа учетных данных](./feature-details/selecting-a-credential-type.md)
- [Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Работа с сертификатами](./feature-details/working-with-certificates.md)
- [Практическое руководство. Создание клиента](how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<message>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md)
