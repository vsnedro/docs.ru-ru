---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614736"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="29aab-101">X509CertificateClaimSet.FindClaims учитывает все аргументы claimType</span><span class="sxs-lookup"><span data-stu-id="29aab-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

#### <a name="details"></a><span data-ttu-id="29aab-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="29aab-102">Details</span></span>

<span data-ttu-id="29aab-103">Если в приложениях, предназначенных для .NET Framework 4.6.1, набор утверждений X509 инициализируется из сертификата, имеющего несколько записей DNS в поле SAN, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> пытается сопоставить аргумент claimType со всеми записями DNS. В приложениях, предназначенных для предыдущих версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> пытается сопоставить аргумент claimType только с последней записью DNS.</span><span class="sxs-lookup"><span data-stu-id="29aab-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument only with the last DNS entry.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="29aab-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="29aab-104">Suggestion</span></span>

<span data-ttu-id="29aab-105">Это изменение затрагивает только приложения, предназначенные для .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="29aab-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="29aab-106">Это изменение можно отключить (или включить, если используются версии, предшествующие 4.6.1) с помощью параметра совместимости [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).</span><span class="sxs-lookup"><span data-stu-id="29aab-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="29aab-107">name</span><span class="sxs-lookup"><span data-stu-id="29aab-107">Name</span></span>    | <span data-ttu-id="29aab-108">Значение</span><span class="sxs-lookup"><span data-stu-id="29aab-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="29aab-109">Область</span><span class="sxs-lookup"><span data-stu-id="29aab-109">Scope</span></span>   | <span data-ttu-id="29aab-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="29aab-110">Minor</span></span>       |
| <span data-ttu-id="29aab-111">Version</span><span class="sxs-lookup"><span data-stu-id="29aab-111">Version</span></span> | <span data-ttu-id="29aab-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="29aab-112">4.6.1</span></span>       |
| <span data-ttu-id="29aab-113">Type</span><span class="sxs-lookup"><span data-stu-id="29aab-113">Type</span></span>    | <span data-ttu-id="29aab-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="29aab-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="29aab-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="29aab-115">Affected APIs</span></span>

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
