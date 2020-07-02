---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622130"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="fd3de-101">Профилирование приложений ASP.Net MVC4 может привести к неустранимой ошибке подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="fd3de-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="fd3de-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="fd3de-102">Details</span></span>

<span data-ttu-id="fd3de-103">Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="fd3de-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fd3de-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="fd3de-104">Suggestion</span></span>

<span data-ttu-id="fd3de-105">Эта проблема решена в .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="fd3de-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="fd3de-106">Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.</span><span class="sxs-lookup"><span data-stu-id="fd3de-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="fd3de-107">name</span><span class="sxs-lookup"><span data-stu-id="fd3de-107">Name</span></span>    | <span data-ttu-id="fd3de-108">Значение</span><span class="sxs-lookup"><span data-stu-id="fd3de-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fd3de-109">Область</span><span class="sxs-lookup"><span data-stu-id="fd3de-109">Scope</span></span>   |<span data-ttu-id="fd3de-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="fd3de-110">Edge</span></span>|
|<span data-ttu-id="fd3de-111">Version</span><span class="sxs-lookup"><span data-stu-id="fd3de-111">Version</span></span>|<span data-ttu-id="fd3de-112">4.5</span><span class="sxs-lookup"><span data-stu-id="fd3de-112">4.5</span></span>|
|<span data-ttu-id="fd3de-113">Type</span><span class="sxs-lookup"><span data-stu-id="fd3de-113">Type</span></span>|<span data-ttu-id="fd3de-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="fd3de-114">Runtime</span></span>|
