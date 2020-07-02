---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616110"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="c3741-101">DbParameter.Precision и DbParameter.Scale теперь являются открытыми виртуальными членами</span><span class="sxs-lookup"><span data-stu-id="c3741-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

#### <a name="details"></a><span data-ttu-id="c3741-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c3741-102">Details</span></span>

<span data-ttu-id="c3741-103"><xref:System.Data.Common.DbParameter.Precision> и <xref:System.Data.Common.DbParameter.Scale> реализованы как открытые виртуальные свойства.</span><span class="sxs-lookup"><span data-stu-id="c3741-103"><xref:System.Data.Common.DbParameter.Precision> and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="c3741-104">Они заменяют соответствующие явные реализации интерфейса: <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> и <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="c3741-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c3741-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c3741-105">Suggestion</span></span>

<span data-ttu-id="c3741-106">При повторном создании поставщика базы данных ADO.NET эти различия потребуют применения ключевого слова override к свойствам Precision и Scale.</span><span class="sxs-lookup"><span data-stu-id="c3741-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="c3741-107">Это требуется только в случае повторного создания компонентов; существующие двоичные файлы будут продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="c3741-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>

| <span data-ttu-id="c3741-108">name</span><span class="sxs-lookup"><span data-stu-id="c3741-108">Name</span></span>    | <span data-ttu-id="c3741-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c3741-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c3741-110">Область</span><span class="sxs-lookup"><span data-stu-id="c3741-110">Scope</span></span>   | <span data-ttu-id="c3741-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="c3741-111">Minor</span></span>       |
| <span data-ttu-id="c3741-112">Version</span><span class="sxs-lookup"><span data-stu-id="c3741-112">Version</span></span> | <span data-ttu-id="c3741-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c3741-113">4.5.1</span></span>       |
| <span data-ttu-id="c3741-114">Type</span><span class="sxs-lookup"><span data-stu-id="c3741-114">Type</span></span>    | <span data-ttu-id="c3741-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="c3741-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c3741-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c3741-116">Affected APIs</span></span>

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
