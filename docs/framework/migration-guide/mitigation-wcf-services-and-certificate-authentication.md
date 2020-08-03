---
title: Устранение рисков. Службы WCF и проверка подлинности сертификатов
description: Узнайте, как устранить проблемы с проверкой подлинности на основе сертификатов, связанные с изменениями в списке протоколов WCF SSL по умолчанию в .NET Framework 4.6.
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: b6460e58bb32151003430d6573c4bcf1b514081b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475376"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="a410f-103">Устранение рисков. Службы WCF и проверка подлинности сертификатов</span><span class="sxs-lookup"><span data-stu-id="a410f-103">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="a410f-104">В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="a410f-104">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="a410f-105">Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="a410f-105">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="a410f-106">Последствия</span><span class="sxs-lookup"><span data-stu-id="a410f-106">Impact</span></span>

<span data-ttu-id="a410f-107">Протокол TLS 1.2 не поддерживает проверку подлинности MD5.</span><span class="sxs-lookup"><span data-stu-id="a410f-107">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="a410f-108">В результате, если пользователь применяет SSL-сертификат, который использует хэш-алгоритм MD5, клиенту WCF не удается подключиться к службе WCF.</span><span class="sxs-lookup"><span data-stu-id="a410f-108">As a result, if a customer uses an SSL certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="a410f-109">Дополнительные сведения см. в разделе [Устранение рисков. Службы WCF и проверка подлинности сертификатов](mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a410f-109">For more information, see [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="a410f-110">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="a410f-110">Mitigation</span></span>

<span data-ttu-id="a410f-111">Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="a410f-111">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="a410f-112">Обновите сертификат, чтобы он не использовал алгоритм MD5.</span><span class="sxs-lookup"><span data-stu-id="a410f-112">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="a410f-113">Это рекомендуемое решение.</span><span class="sxs-lookup"><span data-stu-id="a410f-113">This is the recommended solution.</span></span>

- <span data-ttu-id="a410f-114">Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола.</span><span class="sxs-lookup"><span data-stu-id="a410f-114">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="a410f-115">Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.</span><span class="sxs-lookup"><span data-stu-id="a410f-115">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="a410f-116">Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</span><span class="sxs-lookup"><span data-stu-id="a410f-116">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="a410f-117">Это выполняется в следующем файле конфигурации:</span><span class="sxs-lookup"><span data-stu-id="a410f-117">The following configuration file does this:</span></span>

  ```xml
  <configuration>
      <system.serviceModel>
          <bindings>
              <netTcpBinding>
                  <binding>
                      <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                          <transport clientCredentialType="None|Windows|Certificate"
                                              protectionLevel="None|Sign|EncryptAndSign"
                                              sslProtocols="Ssl3|Tls1|Tls11">
                          </transport>
                      </security>
                  </binding>
              </netTcpBinding>
          </bindings>
      </system.serviceModel>
  </configuration>
  ```

- <span data-ttu-id="a410f-118">Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) или более ранней версии протокола в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="a410f-118">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="a410f-119">Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</span><span class="sxs-lookup"><span data-stu-id="a410f-119">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="a410f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a410f-120">See also</span></span>

- [<span data-ttu-id="a410f-121">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="a410f-121">Application compatibility</span></span>](application-compatibility.md)
