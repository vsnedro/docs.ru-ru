---
ms.openlocfilehash: a133c2ea48df11915f8708029c70549e8a1ccefd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496438"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="02824-101">Окна WPF отображаются без обрезки, если изображение выходит за пределы одного монитора</span><span class="sxs-lookup"><span data-stu-id="02824-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="02824-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="02824-102">Details</span></span>

<span data-ttu-id="02824-103">В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.</span><span class="sxs-lookup"><span data-stu-id="02824-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="02824-104">Это отличается от предыдущих версий .NET Framework, где окна WPF обрезались, если выходили за пределы одного экрана.</span><span class="sxs-lookup"><span data-stu-id="02824-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="02824-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="02824-105">Suggestion</span></span>

<span data-ttu-id="02824-106">Это поведение (отсутствие или наличие обрезки) можно задать явным образом с помощью элемента <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> в <code>&lt;appSettings&gt;</code> в файле конфигурации приложения или задав свойство <code>EnableMultiMonitorDisplayClipping</code> при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="02824-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="02824-107">name</span><span class="sxs-lookup"><span data-stu-id="02824-107">Name</span></span>    | <span data-ttu-id="02824-108">Значение</span><span class="sxs-lookup"><span data-stu-id="02824-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="02824-109">Область</span><span class="sxs-lookup"><span data-stu-id="02824-109">Scope</span></span>   |<span data-ttu-id="02824-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="02824-110">Minor</span></span>|
|<span data-ttu-id="02824-111">Version</span><span class="sxs-lookup"><span data-stu-id="02824-111">Version</span></span>|<span data-ttu-id="02824-112">4.6</span><span class="sxs-lookup"><span data-stu-id="02824-112">4.6</span></span>|
|<span data-ttu-id="02824-113">Type</span><span class="sxs-lookup"><span data-stu-id="02824-113">Type</span></span>|<span data-ttu-id="02824-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="02824-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="02824-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="02824-115">Affected APIs</span></span>

<span data-ttu-id="02824-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="02824-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
