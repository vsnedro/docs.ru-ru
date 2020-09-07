---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496137"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Исправлено зависание, если ListBox содержит повторяющиеся типы значений

#### <a name="details"></a>Подробнее

Устранена проблема, при которой виртуализация <xref:System.Windows.Controls.ItemsControl> приводила к зависанию при прокрутке, когда коллекция элементов содержит повторяющиеся объекты типов значений.

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.8|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
