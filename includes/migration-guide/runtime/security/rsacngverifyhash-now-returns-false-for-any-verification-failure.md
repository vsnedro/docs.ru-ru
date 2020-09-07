---
ms.openlocfilehash: b7b16e39fa5df9732fa769f2bcd3696dff3b2a49
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497716"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6.2 этот метод возвращает **False**, если сама подпись неверно форматирована. Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, если сама подпись имеет неправильный формат.

#### <a name="suggestion"></a>Предложение

Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает **False**.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
