---
ms.openlocfilehash: b3bf169f60279d245568367afb0bfe004c4ebcd7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275132"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng и DSACng снова могут использоваться в сценариях частичного доверия

|   |   |
|---|---|
|Подробнее|CngLightup (используется в нескольких высокоуровневых API шифрования, таких как <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) и <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> в некоторых случаях требуют полного доверия. К ним относятся вызовы P/Invoke без утверждения разрешений <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>, а также пути кода, в которых <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> предъявляет требования к разрешениям для <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>. Начиная с версии .NET Framework 4.6.2, CngLightup по возможности используется для переключения на <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>. В результате приложения с частичным доверием, которые успешно использовали <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>, могут завершаться сбоем с исключениями <xref:System.Security.SecurityException>. Это изменение добавляет необходимые утверждения, благодаря чему все функции, использующие CngLightup, получают соответствующие разрешения.|
|Предложение|Если это изменение в .NET Framework 4.6.2 затронуло ваши приложения с частичным доверием, выполните обновление до версии .NET Framework 4.7.1.|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
