---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497188"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="bdd5a-101">Адаптеры потока WinRT больше не вызывают FlushAsync автоматически при закрытии</span><span class="sxs-lookup"><span data-stu-id="bdd5a-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="bdd5a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bdd5a-102">Details</span></span>

<span data-ttu-id="bdd5a-103">В приложениях для магазина Windows адаптеры потока среды выполнения Windows больше не вызывают метод FlushAsync из метода Dispose.</span><span class="sxs-lookup"><span data-stu-id="bdd5a-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bdd5a-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="bdd5a-104">Suggestion</span></span>

<span data-ttu-id="bdd5a-105">Это изменение должно быть прозрачным.</span><span class="sxs-lookup"><span data-stu-id="bdd5a-105">This change should be transparent.</span></span> <span data-ttu-id="bdd5a-106">Разработчики могут восстановить прежнее поведение, написав следующий код.</span><span class="sxs-lookup"><span data-stu-id="bdd5a-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="bdd5a-107">name</span><span class="sxs-lookup"><span data-stu-id="bdd5a-107">Name</span></span>    | <span data-ttu-id="bdd5a-108">Значение</span><span class="sxs-lookup"><span data-stu-id="bdd5a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bdd5a-109">Область</span><span class="sxs-lookup"><span data-stu-id="bdd5a-109">Scope</span></span>   |<span data-ttu-id="bdd5a-110">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="bdd5a-110">Transparent</span></span>|
|<span data-ttu-id="bdd5a-111">Version</span><span class="sxs-lookup"><span data-stu-id="bdd5a-111">Version</span></span>|<span data-ttu-id="bdd5a-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="bdd5a-112">4.5.1</span></span>|
|<span data-ttu-id="bdd5a-113">Type</span><span class="sxs-lookup"><span data-stu-id="bdd5a-113">Type</span></span>|<span data-ttu-id="bdd5a-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="bdd5a-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bdd5a-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bdd5a-115">Affected APIs</span></span>

<span data-ttu-id="bdd5a-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="bdd5a-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
