---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496954"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Поддержка нотации специального относительного URI при наличии символов Юникода

#### <a name="details"></a>Подробнее

<xref:System.Uri> больше не будет создавать исключение <xref:System.NullReferenceException> при вызове <xref:System.Uri.TryCreate%2A> для определенных относительных URI, содержащих символы Юникода. Простое воспроизведение <xref:System.NullReferenceException> представлено ниже (с двумя эквивалентными инструкциями):<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Для воспроизведения <xref:System.NullReferenceException> должны выполняться следующие условия:<ul><li>URI должен быть указан как относительный: с префиксом "http:", за которым не следуют две косые черты "//".</li><li>URI должен содержать незарезервированные символы или символы Юникода, закодированные процентами.</li></ul>

#### <a name="suggestion"></a>Предложение

Пользователям, зависящим от этого поведения, для запрета относительных URI следует указывать <xref:System.UriKind.Absolute?displayProperty=nameWithType> при создании URI.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
