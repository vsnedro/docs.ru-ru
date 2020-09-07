---
ms.openlocfilehash: fd9f4f3de8f7be39242d4ff6924d480f20a1a06b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497659"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a><span data-ttu-id="331e0-101">SqlBulkCopy использует кодировку целевого столбца для строк</span><span class="sxs-lookup"><span data-stu-id="331e0-101">SqlBulkCopy uses destination column encoding for strings</span></span>

#### <a name="details"></a><span data-ttu-id="331e0-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="331e0-102">Details</span></span>

<span data-ttu-id="331e0-103">При вставке данных в столбец <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> использует кодировку целевого столбца, а не кодировку по умолчанию для типов <code>VARCHAR</code> и <code>CHAR</code>.</span><span class="sxs-lookup"><span data-stu-id="331e0-103">When inserting data into a column, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> uses the encoding of the destination column rather than the default encoding for <code>VARCHAR</code> and <code>CHAR</code> types.</span></span> <span data-ttu-id="331e0-104">Это изменение исключает возможность повреждения данных, вызванного использованием кодировки по умолчанию, если в целевом столбце не используется кодировка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="331e0-104">This change eliminates the possibility of data corruption caused by using the default encoding when the destination column does not use the default encoding.</span></span> <span data-ttu-id="331e0-105">В редких случаях существующее приложение может создавать исключение SqlException, если при изменении кодировки создаются слишком большие для целевого столбца данные.</span><span class="sxs-lookup"><span data-stu-id="331e0-105">In rare cases, an existing application may throw a SqlException exception if the change in encoding produces data that is too big to fit into the destination column.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="331e0-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="331e0-106">Suggestion</span></span>

<span data-ttu-id="331e0-107">Учитывайте, что <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> больше не будет повреждать данные из-за различий в кодировке.</span><span class="sxs-lookup"><span data-stu-id="331e0-107">Expect that <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> will no longer corrupt data due to encoding differences.</span></span> <span data-ttu-id="331e0-108">Если размер копируемых строк близок к установленному для целевого столбца ограничению, может потребоваться предварительное кодирование данных (с целью копирования для проверки того, что они поместятся в целевом столбце) или перехват исключений <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="331e0-108">If strings near the destination column's size limit are being copied, it may be necessary to either pre-encode data (to be copied to check that the data will fit in the destination column) or catch <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="331e0-109">name</span><span class="sxs-lookup"><span data-stu-id="331e0-109">Name</span></span>    | <span data-ttu-id="331e0-110">Значение</span><span class="sxs-lookup"><span data-stu-id="331e0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="331e0-111">Область</span><span class="sxs-lookup"><span data-stu-id="331e0-111">Scope</span></span>   |<span data-ttu-id="331e0-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="331e0-112">Edge</span></span>|
|<span data-ttu-id="331e0-113">Version</span><span class="sxs-lookup"><span data-stu-id="331e0-113">Version</span></span>|<span data-ttu-id="331e0-114">4.5</span><span class="sxs-lookup"><span data-stu-id="331e0-114">4.5</span></span>|
|<span data-ttu-id="331e0-115">Type</span><span class="sxs-lookup"><span data-stu-id="331e0-115">Type</span></span>|<span data-ttu-id="331e0-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="331e0-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="331e0-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="331e0-117">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)>

<!--

#### Affected APIs

- `T:System.Data.SqlClient.SqlBulkCopy`
- `M:System.Data.SqlClient.SqlBulkCopy.#ctor(System.Data.SqlClient.SqlConnection)`

-->
