---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614790"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a>Сериализация управляющих символов с помощью DataContractJsonSerializer теперь совместима с ECMAScript версии 6 и 8

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.2 и более ранних версиях объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> сериализовал некоторые специальные управляющие символы, например \b, \f и \t, не так, как требуют стандарты ECMAScript версии 6 и 8. Начиная с .NET Framework 4.7, сериализация таких управляющих символов совместима с ECMAScript версий 6 и 8.

#### <a name="suggestion"></a>Предложение

В приложениях, предназначенных для .NET Framework 4.7, эта функция включена по умолчанию. Если оно нежелательно, данную функцию можно отключить, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
