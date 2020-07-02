---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621191"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Теперь поддерживаются категории стандартной версии Юникода 8.0

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.2 данные Юникода были обновлены со стандартной версии 6.3 до версии 8.0.  При запросе категорий символов Юникода в .NET Framework 4.6.2 некоторые результаты могут не соответствовать результатам в предыдущих версиях .NET Framework.  Это изменение в первую очередь влияет на слоги языка чероки, а также знаки гласных и обозначения тонов в новой письменности Тай-Лю.

#### <a name="suggestion"></a>Предложение

Просмотрите код и удалите или измените логику, зависящую от жестко заданных категорий символов Юникода.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
