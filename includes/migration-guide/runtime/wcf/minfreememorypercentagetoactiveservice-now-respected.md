---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620649"
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
