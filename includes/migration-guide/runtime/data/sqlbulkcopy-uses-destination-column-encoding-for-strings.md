---
ms.openlocfilehash: fd9f4f3de8f7be39242d4ff6924d480f20a1a06b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497659"
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
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)>

<!--

#### Affected APIs

- `T:System.Data.SqlClient.SqlBulkCopy`
- `M:System.Data.SqlClient.SqlBulkCopy.#ctor(System.Data.SqlClient.SqlConnection)`

-->
