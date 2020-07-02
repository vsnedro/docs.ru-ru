---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616110"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision и DbParameter.Scale теперь являются открытыми виртуальными членами

#### <a name="details"></a>Подробнее

<xref:System.Data.Common.DbParameter.Precision> и <xref:System.Data.Common.DbParameter.Scale> реализованы как открытые виртуальные свойства. Они заменяют соответствующие явные реализации интерфейса: <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> и <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.

#### <a name="suggestion"></a>Предложение

При повторном создании поставщика базы данных ADO.NET эти различия потребуют применения ключевого слова override к свойствам Precision и Scale. Это требуется только в случае повторного создания компонентов; существующие двоичные файлы будут продолжать работать.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
