---
ms.openlocfilehash: 1329a86db4227f75dfba7c50bbbdc2fc23099528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620600"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy использует кодировку целевого столбца для строк

#### <a name="details"></a>Подробнее

При вставке данных в столбец <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> использует кодировку целевого столбца, а не кодировку по умолчанию для типов <code>VARCHAR</code> и <code>CHAR</code>. Это изменение исключает возможность повреждения данных, вызванного использованием кодировки по умолчанию, если в целевом столбце не используется кодировка по умолчанию. В редких случаях существующее приложение может создавать исключение SqlException, если при изменении кодировки создаются слишком большие для целевого столбца данные.

#### <a name="suggestion"></a>Предложение

Учитывайте, что <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> больше не будет повреждать данные из-за различий в кодировке. Если размер копируемых строк близок к установленному для целевого столбца ограничению, может потребоваться предварительное кодирование данных (с целью копирования для проверки того, что они поместятся в целевом столбце) или перехват исключений <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)></li></ul>|
