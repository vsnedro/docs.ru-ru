---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496205"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>EventListeners трассировки событий Windows не выполняют запись событий от поставщиков с явными ключевыми словами (например, от поставщика TPL)

#### <a name="details"></a>Подробнее

EventListeners трассировки событий Windows с пустой маской ключевого слова неправильно записывают события от поставщиков с явными ключевыми словами. В платформе .NET Framework 4.5 поставщик TPL начал предоставлять явные ключевые слова и привел к возникновению этой проблемы. В .NET Framework 4.6 EventListeners были обновлены, чтобы больше не вызывать эту проблему.

#### <a name="suggestion"></a>Предложение

Чтобы обойти эту проблему, замените вызовы <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> вызовами к перегрузке EnableEvents, которая явно задает маску &quot;любые ключевые слова&quot;: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
