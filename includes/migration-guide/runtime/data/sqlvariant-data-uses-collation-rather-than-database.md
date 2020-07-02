---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620606"
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
