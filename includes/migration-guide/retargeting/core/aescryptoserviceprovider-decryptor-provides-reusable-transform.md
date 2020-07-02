---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614657"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>Дешифратор AesCryptoServiceProvider предоставляет преобразование для повторного использования

#### <a name="details"></a>Подробнее

Начиная с приложений, предназначенных для .NET Framework 4.6.2, дешифратор <xref:System.Security.Cryptography.AesCryptoServiceProvider> возвращает преобразование, которое можно использовать повторно. Это преобразование повторно инициализируется после вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> и его можно использовать снова. В приложениях, предназначенных для более ранних версий платформы .NET Framework, попытка повторного использования дешифратора путем вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> после вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> приводит к исключению <xref:System.Security.Cryptography.CryptographicException> или к повреждению данных.

#### <a name="suggestion"></a>Предложение

Влияние этого изменения должно быть минимальным, поскольку это ожидаемое поведение. В приложениях, которые зависят от прежнего поведения, можно отказаться от его изменения, добавив следующий параметр конфигурации в раздел `<runtime>` файла конфигурации приложения:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением .NET Framework 4.6.2 или более поздних версий. Для этого добавьте в раздел `<runtime>` файла конфигурации приложения следующий параметр:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
