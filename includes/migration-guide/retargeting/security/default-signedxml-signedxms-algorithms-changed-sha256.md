---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614811"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Алгоритмы SignedXML и SignedXMS по умолчанию изменены на SHA256

#### <a name="details"></a>Подробнее

В .NET Framework 4.7 и более ранних версий SignedXML и SignedCMS по умолчанию изменены на SHA-1 для некоторых операций. Начиная с .NET Framework 4.7.1 по умолчанию для этих операций включен SHA256. Это изменение было необходимо, поскольку алгоритм SHA-1 больше не считается безопасным.

#### <a name="suggestion"></a>Предложение

Существует два новых значения переключения контекста для выбора алгоритма SHA-1 (небезопасно) или SHA256 по умолчанию:

- Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms
- Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms Если в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, использовать SHA256 нежелательно, можно изменить алгоритм по умолчанию на SHA1, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

В приложениях, предназначенных для .NET Framework 4.7 и более ранних версий, вы можете выбрать это изменение, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Версия | 4.7.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
