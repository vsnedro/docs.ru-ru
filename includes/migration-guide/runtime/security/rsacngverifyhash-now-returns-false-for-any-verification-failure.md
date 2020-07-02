---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621204"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6.2 этот метод возвращает **False**, если сама подпись неверно форматирована. Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, если сама подпись имеет неправильный формат.

#### <a name="suggestion"></a>Предложение

Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает **False**.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
