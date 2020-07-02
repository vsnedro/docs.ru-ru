---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621204"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="0a76e-101">RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки</span><span class="sxs-lookup"><span data-stu-id="0a76e-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="0a76e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0a76e-102">Details</span></span>

<span data-ttu-id="0a76e-103">Начиная с .NET Framework 4.6.2 этот метод возвращает **False**, если сама подпись неверно форматирована.</span><span class="sxs-lookup"><span data-stu-id="0a76e-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="0a76e-104">Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, если сама подпись имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="0a76e-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0a76e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0a76e-105">Suggestion</span></span>

<span data-ttu-id="0a76e-106">Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает **False**.</span><span class="sxs-lookup"><span data-stu-id="0a76e-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="0a76e-107">name</span><span class="sxs-lookup"><span data-stu-id="0a76e-107">Name</span></span>    | <span data-ttu-id="0a76e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="0a76e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0a76e-109">Область</span><span class="sxs-lookup"><span data-stu-id="0a76e-109">Scope</span></span>   |<span data-ttu-id="0a76e-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="0a76e-110">Minor</span></span>|
|<span data-ttu-id="0a76e-111">Version</span><span class="sxs-lookup"><span data-stu-id="0a76e-111">Version</span></span>|<span data-ttu-id="0a76e-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0a76e-112">4.6.2</span></span>|
|<span data-ttu-id="0a76e-113">Type</span><span class="sxs-lookup"><span data-stu-id="0a76e-113">Type</span></span>|<span data-ttu-id="0a76e-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0a76e-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0a76e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0a76e-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
