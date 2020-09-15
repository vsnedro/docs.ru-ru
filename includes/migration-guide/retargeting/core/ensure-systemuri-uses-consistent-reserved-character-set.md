---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614664"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Гарантия использования System.Uri согласованного набора зарезервированных символов

#### <a name="details"></a>Подробнее

В <xref:System.Uri?displayProperty=fullName> некоторые символы, закодированные процентами, которые иногда декодировались, теперь всегда остаются закодированными. Это справедливо для свойств и методов, которые получают доступ к компонентам пути, запроса, фрагмента или сведений пользователя URI. Это поведение изменится, только если выполняются оба указанные ниже условия:

- URI содержит кодированную форму любого из следующих зарезервированных символов: `:`, `'`, `(`, `)`, `!` или `*`.
- URI содержит строку в кодировке Юникоде или закодированные незарезервированные символы. Если выполняются оба приведенных выше условия, закодированные зарезервированные символы остаются закодированными. В предыдущих версиях .NET Framework они декодировались.

#### <a name="suggestion"></a>Предложение

Для приложений, предназначенных для версий платформы .NET Framework, начиная с 4.7.2, новое поведение декодирования включено по умолчанию. Если это изменение нежелательно, можно отключить его, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

Для приложений, предназначенных для более ранних версий .NET Framework, но выполняемых в версиях начиная с .NET Framework 4.7.2, новое поведение декодирования отключено по умолчанию. Вы можете включить это изменение, добавив следующий параметр [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri?displayProperty=nameWithType>
