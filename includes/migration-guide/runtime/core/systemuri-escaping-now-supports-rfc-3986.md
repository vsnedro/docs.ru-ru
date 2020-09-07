---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496347"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>Экранирование System.Uri теперь поддерживает RFC 3986

#### <a name="details"></a>Подробнее

Экранирование URI изменилось в .NET Framework 4.5 для поддержки [RFC 3986](https://tools.ietf.org/html/rfc3986). Внесены следующие конкретные изменения.<ul><li>Метод <xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> преобразует в escape-последовательность зарезервированные символы в соответствии с RFC 3986.</li><li>Метод <xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> не преобразует в escape-последовательность зарезервированные символы.</li><li>Метод <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> не создает исключение, если ему встречается неверная escape-последовательность.</li><li>Преобразование незарезервированных символов в escape-символы отменяется.</li></ul>

#### <a name="suggestion"></a>Предложение

<ul><li>Обновления приложений не зависят от <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> для создания исключения в случае недопустимой escape-последовательности. Такие последовательности должны обнаруживаться сразу же.</li><li>Аналогичным образом ожидается, что экранированные и неэкранированные URI и строки данных могут отличаться в .NET Framework 4.0 и .NET Framework 4.5 и их не следует сравнивать в версиях .NET напрямую. Их необходимо проанализировать и нормализовать в одной версии .NET перед выполнением каких-либо сравнений.</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
