---
ms.openlocfilehash: 7d50962b518c15875a5f1a82f5b89ab87a1db02e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620571"
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
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
