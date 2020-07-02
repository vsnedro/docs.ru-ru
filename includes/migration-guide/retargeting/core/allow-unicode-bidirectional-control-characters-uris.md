---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614633"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Разрешить двунаправленные управляющие символы Юникода в URI

#### <a name="details"></a>Подробнее

Юникод определяет несколько специальных управляющих символов, используемых для указания ориентации текста. В предыдущих версиях платформы .NET Framework эти символы ошибочно удалялись из всех URI, даже если были представлены в процентной кодировке. В целях соблюдения стандарта [RFC 3987](https://tools.ietf.org/html/rfc3987) теперь мы разрешаем эти символы в URI. При обнаружении незакодированных символов в URI выполняется процентное кодирование. Символы в процентной кодировке остаются без изменений.

#### <a name="suggestion"></a>Предложение

Для приложений, предназначенных для версий .NET Framework начиная с 4.7.2, поддержка двунаправленных символов Юникода включена по умолчанию. Если это изменение нежелательно, можно отключить его, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

Для приложений, предназначенных для более ранних версий .NET Framework, но выполняемых в версиях начиная с .NET Framework 4.7.2, поддержка двунаправленных символов Юникода отключена по умолчанию. Вы можете включить это изменение, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri?displayProperty=nameWithType>
