---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614736"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims учитывает все аргументы claimType

#### <a name="details"></a>Подробнее

Если в приложениях, предназначенных для .NET Framework 4.6.1, набор утверждений X509 инициализируется из сертификата, имеющего несколько записей DNS в поле SAN, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> пытается сопоставить аргумент claimType со всеми записями DNS. В приложениях, предназначенных для предыдущих версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> пытается сопоставить аргумент claimType только с последней записью DNS.

#### <a name="suggestion"></a>Предложение

Это изменение затрагивает только приложения, предназначенные для .NET Framework 4.6.1. Это изменение можно отключить (или включить, если используются версии, предшествующие 4.6.1) с помощью параметра совместимости [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
