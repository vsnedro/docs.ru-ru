---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497191"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>Параметр MinFreeMemoryPercentageToActiveService теперь учитывается

#### <a name="details"></a>Подробнее

Этот параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF. Он предназначен для предотвращения исключений <xref:System.OutOfMemoryException?displayProperty=fullName>. В .NET Framework 4.5 этот параметр не оказывал никакого влияния. В .NET Framework 4.5.1 этот параметр уже используется.

#### <a name="suggestion"></a>Предложение

Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации. Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.

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
