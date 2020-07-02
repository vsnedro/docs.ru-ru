---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620631"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a>Enumerable.Empty&lt;TResult&gt; всегда возвращает кэшированный экземпляр

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.5 <xref:System.Linq.Enumerable.Empty%60%601> всегда возвращает кэшированный внутренний экземпляр <xref:System.Collections.Generic.IEnumerable%601>. Ранее <xref:System.Linq.Enumerable.Empty%60%601> кэшировал пустой <xref:System.Collections.Generic.IEnumerable%601> в момент вызова API, и в некоторых ситуациях, когда <xref:System.Linq.Enumerable.Empty%60%601> вызывался быстро и параллельно, для различных вызовов API могли возвращаться разные экземпляры типа.

#### <a name="suggestion"></a>Предложение

Так как прежнее поведение было недетерминированным, код вряд ли зависит от него. Однако в том маловероятном случае, когда выполняется сравнение пустых перечислений и ожидается, что они будут неравными, следует создать явные пустые массивы (<code>new T[0]</code>) и не использовать <xref:System.Linq.Enumerable.Empty%60%601>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
