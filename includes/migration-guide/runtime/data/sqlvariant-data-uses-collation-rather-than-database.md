---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497491"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>В данных Sql_variant используется сортировка sql_variant, а не сортировка базы данных

#### <a name="details"></a>Подробнее

В данных <code>sql_variant</code> используется сортировка <code>sql_variant</code>, а не сортировка базы данных.

#### <a name="suggestion"></a>Предложение

Это изменение предотвращает возможное повреждение данных, если сортировка базы данных отличается от сортировки <code>sql_variant</code>. В приложениях, в которых предполагается, что данные будут повреждены, могут возникать сбои.

| name    | Значение       |
|:--------|:------------|
| Область   |Прозрачный|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
