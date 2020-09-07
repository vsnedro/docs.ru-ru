---
ms.openlocfilehash: afcb9b950d4c47b4251dcc8ab0cf9cfc702005c8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497828"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a>Службы WCF, использующие NETTCP с уровнем безопасности SSL и проверкой подлинности на основе сертификатов MD5

#### <a name="details"></a>Подробнее

В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2. Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2. Протокол TLS 1.2 не поддерживает проверку подлинности на основе сертификатов MD5. Поэтому, если используется сертификат MD5, клиент WCF не сможет подключиться к службе WCF.

#### <a name="suggestion"></a>Предложение

Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.

- Обновите сертификат, чтобы он не использовал алгоритм MD5. Это рекомендуемое решение.
- Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола. Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.

> [!WARNING]
> Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.

Это выполняется в следующем файле конфигурации:

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) или более ранней версии протокола в исходном коде.

> [!WARNING]
> Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.

| name    | Значение   |
|:--------|:--------|
| Область   | Дополнительный номер   |
| Version | 4.6     |
| Type    | Среда выполнения |

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
