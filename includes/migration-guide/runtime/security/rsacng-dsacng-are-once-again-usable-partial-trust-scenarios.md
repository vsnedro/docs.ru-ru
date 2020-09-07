---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497028"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a><span data-ttu-id="f3e1d-101">RSACng и DSACng снова могут использоваться в сценариях частичного доверия</span><span class="sxs-lookup"><span data-stu-id="f3e1d-101">RSACng and DSACng are once again usable in Partial Trust scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="f3e1d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f3e1d-102">Details</span></span>

<span data-ttu-id="f3e1d-103">CngLightup (используется в нескольких высокоуровневых API шифрования, таких как <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) и <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> в некоторых случаях требуют полного доверия.</span><span class="sxs-lookup"><span data-stu-id="f3e1d-103">CngLightup (used in several higher-level crypto apis, such as <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) and <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> in some cases rely on full trust.</span></span> <span data-ttu-id="f3e1d-104">К ним относятся вызовы P/Invoke без утверждения разрешений <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>, а также пути кода, в которых <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> предъявляет требования к разрешениям для <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f3e1d-104">These include P/Invokes without asserting <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> permissions, and code paths where <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> has permission demands for <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f3e1d-105">Начиная с версии .NET Framework 4.6.2, CngLightup по возможности используется для переключения на <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f3e1d-105">Starting with the .NET Framework 4.6.2, CngLightup was used to switch to <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wherever possible.</span></span> <span data-ttu-id="f3e1d-106">В результате приложения с частичным доверием, которые успешно использовали <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>, могут завершаться сбоем с исключениями <xref:System.Security.SecurityException>. Это изменение добавляет необходимые утверждения, благодаря чему все функции, использующие CngLightup, получают соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="f3e1d-106">As a result, partial trust apps that successfully used <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> began to fail and throw <xref:System.Security.SecurityException> exceptions.This change adds the required asserts so that all functions using CngLightup have the required permissions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f3e1d-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="f3e1d-107">Suggestion</span></span>

<span data-ttu-id="f3e1d-108">Если это изменение в .NET Framework 4.6.2 затронуло ваши приложения с частичным доверием, выполните обновление до версии .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="f3e1d-108">If this change in the .NET Framework 4.6.2 has negatively impacted your partial trust apps, upgrade to the .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="f3e1d-109">Имя</span><span class="sxs-lookup"><span data-stu-id="f3e1d-109">Name</span></span>    | <span data-ttu-id="f3e1d-110">Значение</span><span class="sxs-lookup"><span data-stu-id="f3e1d-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f3e1d-111">Область</span><span class="sxs-lookup"><span data-stu-id="f3e1d-111">Scope</span></span>   |<span data-ttu-id="f3e1d-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="f3e1d-112">Edge</span></span>|
|<span data-ttu-id="f3e1d-113">Version</span><span class="sxs-lookup"><span data-stu-id="f3e1d-113">Version</span></span>|<span data-ttu-id="f3e1d-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f3e1d-114">4.6.2</span></span>|
|<span data-ttu-id="f3e1d-115">Type</span><span class="sxs-lookup"><span data-stu-id="f3e1d-115">Type</span></span>|<span data-ttu-id="f3e1d-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f3e1d-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f3e1d-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f3e1d-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.DSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.DSACng.Key`
- `P:System.Security.Cryptography.DSACng.LegalKeySizes`
- `M:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])`
- `M:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])`
- `M:System.Security.Cryptography.RSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.RSACng.Key`
- `M:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)`
- `M:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
