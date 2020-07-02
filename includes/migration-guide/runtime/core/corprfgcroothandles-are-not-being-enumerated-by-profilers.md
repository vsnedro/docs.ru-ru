---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620558"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="e105a-101">Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="e105a-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="e105a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e105a-102">Details</span></span>

<span data-ttu-id="e105a-103">В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="e105a-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="e105a-104">Эта проблема решена в .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="e105a-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e105a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e105a-105">Suggestion</span></span>

<span data-ttu-id="e105a-106">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e105a-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="e105a-107">name</span><span class="sxs-lookup"><span data-stu-id="e105a-107">Name</span></span>    | <span data-ttu-id="e105a-108">Значение</span><span class="sxs-lookup"><span data-stu-id="e105a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e105a-109">Область</span><span class="sxs-lookup"><span data-stu-id="e105a-109">Scope</span></span>   |<span data-ttu-id="e105a-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e105a-110">Minor</span></span>|
|<span data-ttu-id="e105a-111">Version</span><span class="sxs-lookup"><span data-stu-id="e105a-111">Version</span></span>|<span data-ttu-id="e105a-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e105a-112">4.5.1</span></span>|
|<span data-ttu-id="e105a-113">Type</span><span class="sxs-lookup"><span data-stu-id="e105a-113">Type</span></span>|<span data-ttu-id="e105a-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e105a-114">Runtime</span></span>|
