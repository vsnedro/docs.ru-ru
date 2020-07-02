---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620606"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="19c76-101">В данных Sql_variant используется сортировка sql_variant, а не сортировка базы данных</span><span class="sxs-lookup"><span data-stu-id="19c76-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="19c76-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="19c76-102">Details</span></span>

<span data-ttu-id="19c76-103">В данных <code>sql_variant</code> используется сортировка <code>sql_variant</code>, а не сортировка базы данных.</span><span class="sxs-lookup"><span data-stu-id="19c76-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="19c76-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="19c76-104">Suggestion</span></span>

<span data-ttu-id="19c76-105">Это изменение предотвращает возможное повреждение данных, если сортировка базы данных отличается от сортировки <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="19c76-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="19c76-106">В приложениях, в которых предполагается, что данные будут повреждены, могут возникать сбои.</span><span class="sxs-lookup"><span data-stu-id="19c76-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="19c76-107">name</span><span class="sxs-lookup"><span data-stu-id="19c76-107">Name</span></span>    | <span data-ttu-id="19c76-108">Значение</span><span class="sxs-lookup"><span data-stu-id="19c76-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="19c76-109">Область</span><span class="sxs-lookup"><span data-stu-id="19c76-109">Scope</span></span>   |<span data-ttu-id="19c76-110">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="19c76-110">Transparent</span></span>|
|<span data-ttu-id="19c76-111">Version</span><span class="sxs-lookup"><span data-stu-id="19c76-111">Version</span></span>|<span data-ttu-id="19c76-112">4.5</span><span class="sxs-lookup"><span data-stu-id="19c76-112">4.5</span></span>|
|<span data-ttu-id="19c76-113">Type</span><span class="sxs-lookup"><span data-stu-id="19c76-113">Type</span></span>|<span data-ttu-id="19c76-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="19c76-114">Runtime</span></span>|
