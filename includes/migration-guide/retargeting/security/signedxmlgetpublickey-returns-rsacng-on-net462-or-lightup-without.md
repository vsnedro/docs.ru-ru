---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616096"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey возвращает RSACng в net462 (или lightup) без изменения целевой платформы

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6.2 конкретный тип объекта, возвращаемого методом <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType>, изменен (без особенностей) с реализации CryptoServiceProvider на реализацию Cng. Это связано с изменениями реализации, предусматривающими использование `certificate.PublicKey.Key` вместо внутреннего `certificate.GetAnyPublicKey` с переадресацией к <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.

#### <a name="suggestion"></a>Предложение

Начиная с приложений, выполняющихся в .NET Framework 4.7.1, вы можете использовать реализацию CryptoServiceProvider, используемую по умолчанию на платформе .NET Framework 4.6.1 и более ранних версий, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
