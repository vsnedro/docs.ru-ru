---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620576"
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
