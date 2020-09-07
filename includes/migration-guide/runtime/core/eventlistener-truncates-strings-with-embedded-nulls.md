---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496142"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener усекает строки с внедренными значениями NULL

#### <a name="details"></a>Подробнее

<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> усекает строки с внедренными значениями NULL. Символы NULL не поддерживаются классом <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>. Изменение влияет только на приложения, использующие <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> для чтения данных <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> в процессе и значения NULL в качестве разделителей.

#### <a name="suggestion"></a>Предложение

Если возможно, следует обновить данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>, чтобы не использовать внедренные символы NULL.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
