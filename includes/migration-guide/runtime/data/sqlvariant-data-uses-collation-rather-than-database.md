---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497491"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="48a8c-101">В данных Sql_variant используется сортировка sql_variant, а не сортировка базы данных</span><span class="sxs-lookup"><span data-stu-id="48a8c-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="48a8c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="48a8c-102">Details</span></span>

<span data-ttu-id="48a8c-103">В данных <code>sql_variant</code> используется сортировка <code>sql_variant</code>, а не сортировка базы данных.</span><span class="sxs-lookup"><span data-stu-id="48a8c-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="48a8c-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="48a8c-104">Suggestion</span></span>

<span data-ttu-id="48a8c-105">Это изменение предотвращает возможное повреждение данных, если сортировка базы данных отличается от сортировки <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="48a8c-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="48a8c-106">В приложениях, в которых предполагается, что данные будут повреждены, могут возникать сбои.</span><span class="sxs-lookup"><span data-stu-id="48a8c-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="48a8c-107">name</span><span class="sxs-lookup"><span data-stu-id="48a8c-107">Name</span></span>    | <span data-ttu-id="48a8c-108">Значение</span><span class="sxs-lookup"><span data-stu-id="48a8c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="48a8c-109">Область</span><span class="sxs-lookup"><span data-stu-id="48a8c-109">Scope</span></span>   |<span data-ttu-id="48a8c-110">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="48a8c-110">Transparent</span></span>|
|<span data-ttu-id="48a8c-111">Version</span><span class="sxs-lookup"><span data-stu-id="48a8c-111">Version</span></span>|<span data-ttu-id="48a8c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="48a8c-112">4.5</span></span>|
|<span data-ttu-id="48a8c-113">Type</span><span class="sxs-lookup"><span data-stu-id="48a8c-113">Type</span></span>|<span data-ttu-id="48a8c-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="48a8c-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="48a8c-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="48a8c-115">Affected APIs</span></span>

<span data-ttu-id="48a8c-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="48a8c-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
