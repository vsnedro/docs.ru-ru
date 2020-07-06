---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620565"
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
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
