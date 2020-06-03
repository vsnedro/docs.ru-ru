---
ms.openlocfilehash: 3d94023fc508a56304587121c6cf1444c87b0d52
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721387"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>Увеличен минимальный размер создаваемых ключей RSAOpenSsl

Минимальный размер создаваемых ключей RSA в Linux увеличен с 384 до 512 бит.

#### <a name="change-description"></a>Описание изменений

Начиная с версии .NET Core 3.0, минимальный допустимый размер ключа, сообщаемый свойством `LegalKeySizes` для экземпляров RSA из <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A> и <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> в Linux, увеличился с 384 до 512.

В результате в .NET Core 2.2 и более ранних версий вызов такого метода, как `RSA.Create(384)`, выполняется успешно. В .NET Core 3.0 и более поздних версий при вызове метода `RSA.Create(384)` создается исключение, указывающее на то, что размер слишком мал.

Изменение было внесено, так как для OpenSSL, где выполняются криптографические операции в Linux, между выпусками версий 1.0.2 и 1.1.0 увеличено минимальное значение. В .NET Core 3.0 предпочтительно использовать OpenSSL версий от 1.1.x до 1.0.x. Передаваемый номер версии был повышен в соответствии с повышением лимита для зависимостей.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы вызываете любой затронутый API-интерфейс, убедитесь, что размер созданных ключей не меньше минимального значения, установленного поставщиком.

> [!NOTE]
> Стандарт 384-битового шифрования RSA уже считается небезопасным (как и стандарт 512-битового шифрования). В современных документах, таких как [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf) (Специальная публикация NIST 800-57, часть 1, редакция 4), рекомендуется создавать ключи с минимальным размером 2048 бит.

#### <a name="category"></a>Категория

Шифрование

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A>

<!--
#### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
