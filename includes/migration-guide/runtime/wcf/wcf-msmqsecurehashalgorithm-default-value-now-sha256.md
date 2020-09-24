---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770881"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>MsmqSecureHashAlgorithm WCF теперь по умолчанию имеет значение SHA256

#### <a name="details"></a>Подробные сведения

Начиная с версии .NET Framework 4.7.1, в WCF для подписывания сообщений Msmq по умолчанию используется алгоритм SHA256. В .NET Framework 4.7 и более ранних версий для подписывания сообщений по умолчанию используется алгоритм SHA1.

#### <a name="suggestion"></a>Предложение

Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел `<runtime>` файла app.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| name    | Значение   |
|:--------|:--------|
| Область   | Дополнительный номер   |
| Версия | 4.7.1   |
| Type    | Среда выполнения |

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
