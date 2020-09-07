---
ms.openlocfilehash: afcb9b950d4c47b4251dcc8ab0cf9cfc702005c8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497828"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="2041b-101">Службы WCF, использующие NETTCP с уровнем безопасности SSL и проверкой подлинности на основе сертификатов MD5</span><span class="sxs-lookup"><span data-stu-id="2041b-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="2041b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2041b-102">Details</span></span>

<span data-ttu-id="2041b-103">В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2041b-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="2041b-104">Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2. Протокол TLS 1.2 не поддерживает проверку подлинности на основе сертификатов MD5.</span><span class="sxs-lookup"><span data-stu-id="2041b-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="2041b-105">Поэтому, если используется сертификат MD5, клиент WCF не сможет подключиться к службе WCF.</span><span class="sxs-lookup"><span data-stu-id="2041b-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2041b-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="2041b-106">Suggestion</span></span>

<span data-ttu-id="2041b-107">Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="2041b-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="2041b-108">Обновите сертификат, чтобы он не использовал алгоритм MD5.</span><span class="sxs-lookup"><span data-stu-id="2041b-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="2041b-109">Это рекомендуемое решение.</span><span class="sxs-lookup"><span data-stu-id="2041b-109">This is the recommended solution.</span></span>
- <span data-ttu-id="2041b-110">Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола.</span><span class="sxs-lookup"><span data-stu-id="2041b-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="2041b-111">Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.</span><span class="sxs-lookup"><span data-stu-id="2041b-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="2041b-112">Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</span><span class="sxs-lookup"><span data-stu-id="2041b-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="2041b-113">Это выполняется в следующем файле конфигурации:</span><span class="sxs-lookup"><span data-stu-id="2041b-113">The following configuration file does this:</span></span>

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

- <span data-ttu-id="2041b-114">Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) или более ранней версии протокола в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="2041b-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="2041b-115">Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</span><span class="sxs-lookup"><span data-stu-id="2041b-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="2041b-116">name</span><span class="sxs-lookup"><span data-stu-id="2041b-116">Name</span></span>    | <span data-ttu-id="2041b-117">Значение</span><span class="sxs-lookup"><span data-stu-id="2041b-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="2041b-118">Область</span><span class="sxs-lookup"><span data-stu-id="2041b-118">Scope</span></span>   | <span data-ttu-id="2041b-119">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="2041b-119">Minor</span></span>   |
| <span data-ttu-id="2041b-120">Version</span><span class="sxs-lookup"><span data-stu-id="2041b-120">Version</span></span> | <span data-ttu-id="2041b-121">4.6</span><span class="sxs-lookup"><span data-stu-id="2041b-121">4.6</span></span>     |
| <span data-ttu-id="2041b-122">Type</span><span class="sxs-lookup"><span data-stu-id="2041b-122">Type</span></span>    | <span data-ttu-id="2041b-123">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2041b-123">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2041b-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2041b-124">Affected APIs</span></span>

<span data-ttu-id="2041b-125">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="2041b-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
