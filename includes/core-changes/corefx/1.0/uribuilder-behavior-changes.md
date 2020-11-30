---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032075"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a>Для свойств UriBuilder больше не добавляются начальные символы

<xref:System.UriBuilder.Fragment?displayProperty=nameWithType> больше не добавляет начальный символ `#`, а <xref:System.UriBuilder.Query?displayProperty=nameWithType> больше не добавляет начальный символ `?`, если он уже существует.

#### <a name="change-description"></a>Описание изменений

В .NET Framework свойства <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> и <xref:System.UriBuilder.Query?displayProperty=nameWithType> всегда добавляют к сохраненному значению в начале символ `#` или `?` соответственно. Такое поведение может привести к появлению нескольких символов `#` или `?` в сохраненном значении, если строка уже содержит один из этих начальных символов. Например, значение <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> может стать `##main`.

Начиная с .NET Core 1.0 эти свойства больше не добавляют начальные символы `#` или `?` к сохраненному значению, если в начале строки уже есть начальный символ.

#### <a name="version-introduced"></a>Представленная версия

1.0

#### <a name="recommended-action"></a>Рекомендованное действие

При задании значений свойств больше не нужно явно удалять эти начальные символы. Это особенно полезно при добавлении значений, так как больше не нужно каждый раз удалять начальные символы `#` или `?`.

Например, в следующем фрагменте кода показано различие в поведении между .NET Framework и .NET Core.

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- В .NET Framework выходными данными будет `????one=1&two=2&three=3&four=4`.
- В .NET Core выходными данными будет `?one=1&two=2&three=3&four=4`.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
