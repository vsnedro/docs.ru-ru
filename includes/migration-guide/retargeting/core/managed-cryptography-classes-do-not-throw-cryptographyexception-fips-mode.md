---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616291"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a>Управляемые криптографические классы, которые не вызывают исключение CryptographyException в режиме FIPS

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.2 и более ранних версий управляемые классы поставщиков служб шифрования, такие как <xref:System.Security.Cryptography.SHA256Managed>, выдавали исключение <xref:System.Security.Cryptography.CryptographicException> во время настройки системных библиотек шифрования в режиме FIPS. Эти исключения создаются, так как управляемые версии не прошли сертификацию FIPS 140-2, а также для запрета алгоритмов шифрования, которые не одобрены правилами FIPS.  Так как у некоторых разработчиков компьютеры разработки работают в режиме FIPS, эти исключения часто вызываются только в рабочих системах. Приложения, предназначенные для .NET Framework 4.8 и более поздних версий, автоматически переключаются на более новую и нестрогую политику, чтобы исключение <xref:System.Security.Cryptography.CryptographicException> больше не вызывалось по умолчанию в таких случаях. Вместо этого управляемые классы шифрования перенацеливают криптографические операции на системную библиотеку шифрования. Это изменение политики эффективно устраняет возможное заблуждение относительно различий между средами разработки и рабочими средами, применяя к собственным и управляемым компонентам одну и ту же политику шифрования.

#### <a name="suggestion"></a>Предложение

Если такое поведение нежелательно, вы можете отказаться от него и восстановить предыдущее поведение, чтобы исключение <xref:System.Security.Cryptography.CryptographicException> вызывалось в режиме FIPS, добавив следующий параметр конфигурации [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

Если приложение предназначено для .NET Framework 4.7.2 или более ранних версий, можно также включить это изменение, добавив следующий параметр конфигурации [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.8         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
