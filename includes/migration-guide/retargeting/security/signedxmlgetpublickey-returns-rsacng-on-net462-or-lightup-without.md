---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616096"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a><span data-ttu-id="67cf7-101">SignedXml.GetPublicKey возвращает RSACng в net462 (или lightup) без изменения целевой платформы</span><span class="sxs-lookup"><span data-stu-id="67cf7-101">SignedXml.GetPublicKey returns RSACng on net462 (or lightup) without retargeting change</span></span>

#### <a name="details"></a><span data-ttu-id="67cf7-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="67cf7-102">Details</span></span>

<span data-ttu-id="67cf7-103">Начиная с .NET Framework 4.6.2 конкретный тип объекта, возвращаемого методом <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType>, изменен (без особенностей) с реализации CryptoServiceProvider на реализацию Cng.</span><span class="sxs-lookup"><span data-stu-id="67cf7-103">Starting with the .NET Framework 4.6.2, the concrete type of the object returned by the <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> method changed (without a quirk) from a CryptoServiceProvider implementation to a Cng implementation.</span></span> <span data-ttu-id="67cf7-104">Это связано с изменениями реализации, предусматривающими использование `certificate.PublicKey.Key` вместо внутреннего `certificate.GetAnyPublicKey` с переадресацией к <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67cf7-104">This is because the implementation changed from using `certificate.PublicKey.Key` to using the internal `certificate.GetAnyPublicKey` which forwards to <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67cf7-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="67cf7-105">Suggestion</span></span>

<span data-ttu-id="67cf7-106">Начиная с приложений, выполняющихся в .NET Framework 4.7.1, вы можете использовать реализацию CryptoServiceProvider, используемую по умолчанию на платформе .NET Framework 4.6.1 и более ранних версий, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="67cf7-106">Starting with apps running on the .NET Framework 4.7.1, you can use the CryptoServiceProvider implementation used by default in the .NET Framework 4.6.1 and earlier versions by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| <span data-ttu-id="67cf7-107">name</span><span class="sxs-lookup"><span data-stu-id="67cf7-107">Name</span></span>    | <span data-ttu-id="67cf7-108">Значение</span><span class="sxs-lookup"><span data-stu-id="67cf7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67cf7-109">Область</span><span class="sxs-lookup"><span data-stu-id="67cf7-109">Scope</span></span>   | <span data-ttu-id="67cf7-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="67cf7-110">Edge</span></span>        |
| <span data-ttu-id="67cf7-111">Version</span><span class="sxs-lookup"><span data-stu-id="67cf7-111">Version</span></span> | <span data-ttu-id="67cf7-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="67cf7-112">4.6.2</span></span>       |
| <span data-ttu-id="67cf7-113">Type</span><span class="sxs-lookup"><span data-stu-id="67cf7-113">Type</span></span>    | <span data-ttu-id="67cf7-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="67cf7-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="67cf7-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="67cf7-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
