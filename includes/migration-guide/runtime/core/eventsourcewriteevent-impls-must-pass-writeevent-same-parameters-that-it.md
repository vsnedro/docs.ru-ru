---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497533"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>Реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)

#### <a name="details"></a>Подробнее

В среде выполнения теперь реализуется контракт, определяющий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> и определяющий метод событий ETW, должен вызвать метод <code>EventSource.WriteEvent</code> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.

#### <a name="suggestion"></a>Предложение

Возникает исключение <xref:System.IndexOutOfRangeException?displayProperty=fullName>, если объект <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> считывает данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> в процессе для источника события, нарушающего контракт.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
