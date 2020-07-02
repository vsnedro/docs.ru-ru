---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614712"
---
### <a name="long-path-support"></a>Поддержка длинных путей

#### <a name="details"></a>Подробнее

Начиная с приложений, ориентированных на .NET Framework 4.6.2, поддерживаются длинные пути (до 32 тыс. символов), а ограничение длины пути в 260 символов (или `MAX_PATH`) было удалено. Для приложений, которые перекомпилируются для использования в .NET Framework 4.6.2, кодовые пути, ранее вызывавшие исключение <xref:System.IO.PathTooLongException?displayProperty=fullName>, когда путь превышал 260 символов, теперь будут вызывать исключение <xref:System.IO.PathTooLongException?displayProperty=fullName> только при следующих условиях:

- длина пути превышает <xref:System.Int16.MaxValue> (32 767) символов;
- операционная система возвращает `COR_E_PATHTOOLONG` или его эквивалент;
Для приложений, предназначенных для .NET Framework 4.6.1 и более ранних версий, среда выполнения автоматически создает исключение <xref:System.IO.PathTooLongException?displayProperty=fullName>, когда длина пути превышает 260 символов.

#### <a name="suggestion"></a>Предложение

Для приложений, предназначенных для .NET Framework 4.6.2, можно отказаться от поддержки длинного пути, добавив следующую строку в раздел `<runtime>` файла `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.6.2 или более поздней версии, можно включить поддержку длинного пути, добавив следующую строку в раздел `<runtime>` файла `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |
