---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497655"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a><span data-ttu-id="eb581-101">WPF создает процесс wisptis.exe, который может заблокировать мышь</span><span class="sxs-lookup"><span data-stu-id="eb581-101">WPF spawns a wisptis.exe process which can freeze the mouse</span></span>

#### <a name="details"></a><span data-ttu-id="eb581-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="eb581-102">Details</span></span>

<span data-ttu-id="eb581-103">Проблема появилась в версии 4.5.2 — процесс <code>wisptis.exe</code> создается и блокирует мышь.</span><span class="sxs-lookup"><span data-stu-id="eb581-103">An issue was introduced in 4.5.2 that causes <code>wisptis.exe</code> to be spawned that can freeze mouse input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eb581-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="eb581-104">Suggestion</span></span>

<span data-ttu-id="eb581-105">Исправление этой проблемы доступно в сервисном выпуске платформы .NET Framework 4.5.2 (пакет исправлений 3026376) или через обновление до версии .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="eb581-105">A fix for this issue is available in a servicing release of the .NET Framework 4.5.2 (hotfix rollup 3026376), or by upgrading to the .NET Framework 4.6</span></span>

| <span data-ttu-id="eb581-106">name</span><span class="sxs-lookup"><span data-stu-id="eb581-106">Name</span></span>    | <span data-ttu-id="eb581-107">Значение</span><span class="sxs-lookup"><span data-stu-id="eb581-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eb581-108">Область</span><span class="sxs-lookup"><span data-stu-id="eb581-108">Scope</span></span>   |<span data-ttu-id="eb581-109">Значительно</span><span class="sxs-lookup"><span data-stu-id="eb581-109">Major</span></span>|
|<span data-ttu-id="eb581-110">Version</span><span class="sxs-lookup"><span data-stu-id="eb581-110">Version</span></span>|<span data-ttu-id="eb581-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="eb581-111">4.5.2</span></span>|
|<span data-ttu-id="eb581-112">Type</span><span class="sxs-lookup"><span data-stu-id="eb581-112">Type</span></span>|<span data-ttu-id="eb581-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="eb581-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eb581-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="eb581-114">Affected APIs</span></span>

<span data-ttu-id="eb581-115">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="eb581-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
