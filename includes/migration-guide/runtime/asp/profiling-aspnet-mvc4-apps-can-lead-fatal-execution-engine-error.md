---
ms.openlocfilehash: c679cb2603d39f580203d9373d76481e904e6c1d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496856"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="7d38e-101">Профилирование приложений ASP.Net MVC4 может привести к неустранимой ошибке подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="7d38e-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="7d38e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7d38e-102">Details</span></span>

<span data-ttu-id="7d38e-103">Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="7d38e-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d38e-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="7d38e-104">Suggestion</span></span>

<span data-ttu-id="7d38e-105">Эта проблема решена в .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="7d38e-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="7d38e-106">Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.</span><span class="sxs-lookup"><span data-stu-id="7d38e-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="7d38e-107">name</span><span class="sxs-lookup"><span data-stu-id="7d38e-107">Name</span></span>    | <span data-ttu-id="7d38e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="7d38e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d38e-109">Область</span><span class="sxs-lookup"><span data-stu-id="7d38e-109">Scope</span></span>   |<span data-ttu-id="7d38e-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="7d38e-110">Edge</span></span>|
|<span data-ttu-id="7d38e-111">Version</span><span class="sxs-lookup"><span data-stu-id="7d38e-111">Version</span></span>|<span data-ttu-id="7d38e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7d38e-112">4.5</span></span>|
|<span data-ttu-id="7d38e-113">Type</span><span class="sxs-lookup"><span data-stu-id="7d38e-113">Type</span></span>|<span data-ttu-id="7d38e-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7d38e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7d38e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7d38e-115">Affected APIs</span></span>

<span data-ttu-id="7d38e-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="7d38e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
