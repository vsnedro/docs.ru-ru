---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620630"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="60d74-101">ObjectContext.Translate и ObjectContext.ExecuteStoreQuery теперь поддерживают тип перечисления</span><span class="sxs-lookup"><span data-stu-id="60d74-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="60d74-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="60d74-102">Details</span></span>

<span data-ttu-id="60d74-103">В .NET Framework 4.0 универсальный параметр <code>T</code> методов <code>ObjectContext.Translate</code> и <code>ObjectContext.ExecuteStoreQuery</code> не мог иметь тип перечисления.</span><span class="sxs-lookup"><span data-stu-id="60d74-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="60d74-104">Теперь этот сценарий поддерживается.</span><span class="sxs-lookup"><span data-stu-id="60d74-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="60d74-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="60d74-105">Suggestion</span></span>

<span data-ttu-id="60d74-106">Если метод Translate или ExecuteStoreQuery вызывался для типа перечисления в .NET Framework 4.0, возвращалось значение "0".</span><span class="sxs-lookup"><span data-stu-id="60d74-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="60d74-107">Если такое поведение было желательным, вызовы следовало заменять константой 0 (или его эквивалентом перечисления).</span><span class="sxs-lookup"><span data-stu-id="60d74-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="60d74-108">name</span><span class="sxs-lookup"><span data-stu-id="60d74-108">Name</span></span>    | <span data-ttu-id="60d74-109">Значение</span><span class="sxs-lookup"><span data-stu-id="60d74-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="60d74-110">Область</span><span class="sxs-lookup"><span data-stu-id="60d74-110">Scope</span></span>   |<span data-ttu-id="60d74-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="60d74-111">Edge</span></span>|
|<span data-ttu-id="60d74-112">Version</span><span class="sxs-lookup"><span data-stu-id="60d74-112">Version</span></span>|<span data-ttu-id="60d74-113">4.5</span><span class="sxs-lookup"><span data-stu-id="60d74-113">4.5</span></span>|
|<span data-ttu-id="60d74-114">Type</span><span class="sxs-lookup"><span data-stu-id="60d74-114">Type</span></span>|<span data-ttu-id="60d74-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="60d74-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="60d74-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="60d74-116">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
