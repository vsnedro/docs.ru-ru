---
ms.openlocfilehash: c1e85941c8c6c31c7d937d0671ad955fa6490783
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614652"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng теперь правильно загружает ключи RSA нестандартного размера

#### <a name="details"></a>Подробнее

В версиях .NET Framework до 4.6.2 клиенты с нестандартным размером ключа для сертификатов RSA не могли получить доступ к этим ключам через методы расширения <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> и <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName>.  Возникало исключение <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> с сообщением &quot;Запрошенный размер ключа не поддерживается&quot;. В .NET Framework 4.6.2 эта проблема была устранена. Аналогичным образом <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> и <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> теперь работают с нестандартными размерами ключа, не выдавая исключение <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Если существует логика обработки исключений, которая полагается на предыдущее поведение, когда при использовании ключей нестандартного размера возникало исключение <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, возможно, следует удалить эту логику.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
