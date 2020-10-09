---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607800"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="38445-101">Профилирование приложений ASP.NET MVC4 может привести к неустранимой ошибке подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="38445-101">Profiling ASP.NET MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="38445-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="38445-102">Details</span></span>

<span data-ttu-id="38445-103">Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="38445-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="38445-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="38445-104">Suggestion</span></span>

<span data-ttu-id="38445-105">Эта проблема решена в .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="38445-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="38445-106">Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.</span><span class="sxs-lookup"><span data-stu-id="38445-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="38445-107">name</span><span class="sxs-lookup"><span data-stu-id="38445-107">Name</span></span>    | <span data-ttu-id="38445-108">Значение</span><span class="sxs-lookup"><span data-stu-id="38445-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="38445-109">Область</span><span class="sxs-lookup"><span data-stu-id="38445-109">Scope</span></span>   |<span data-ttu-id="38445-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="38445-110">Edge</span></span>|
|<span data-ttu-id="38445-111">Version</span><span class="sxs-lookup"><span data-stu-id="38445-111">Version</span></span>|<span data-ttu-id="38445-112">4.5</span><span class="sxs-lookup"><span data-stu-id="38445-112">4.5</span></span>|
|<span data-ttu-id="38445-113">Type</span><span class="sxs-lookup"><span data-stu-id="38445-113">Type</span></span>|<span data-ttu-id="38445-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="38445-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="38445-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="38445-115">Affected APIs</span></span>

<span data-ttu-id="38445-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="38445-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
