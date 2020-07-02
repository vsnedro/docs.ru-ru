---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620595"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="4e799-101">Адаптеры потока WinRT больше не вызывают FlushAsync автоматически при закрытии</span><span class="sxs-lookup"><span data-stu-id="4e799-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="4e799-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4e799-102">Details</span></span>

<span data-ttu-id="4e799-103">В приложениях для магазина Windows адаптеры потока среды выполнения Windows больше не вызывают метод FlushAsync из метода Dispose.</span><span class="sxs-lookup"><span data-stu-id="4e799-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4e799-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="4e799-104">Suggestion</span></span>

<span data-ttu-id="4e799-105">Это изменение должно быть прозрачным.</span><span class="sxs-lookup"><span data-stu-id="4e799-105">This change should be transparent.</span></span> <span data-ttu-id="4e799-106">Разработчики могут восстановить прежнее поведение, написав следующий код.</span><span class="sxs-lookup"><span data-stu-id="4e799-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="4e799-107">name</span><span class="sxs-lookup"><span data-stu-id="4e799-107">Name</span></span>    | <span data-ttu-id="4e799-108">Значение</span><span class="sxs-lookup"><span data-stu-id="4e799-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4e799-109">Область</span><span class="sxs-lookup"><span data-stu-id="4e799-109">Scope</span></span>   |<span data-ttu-id="4e799-110">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="4e799-110">Transparent</span></span>|
|<span data-ttu-id="4e799-111">Version</span><span class="sxs-lookup"><span data-stu-id="4e799-111">Version</span></span>|<span data-ttu-id="4e799-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4e799-112">4.5.1</span></span>|
|<span data-ttu-id="4e799-113">Type</span><span class="sxs-lookup"><span data-stu-id="4e799-113">Type</span></span>|<span data-ttu-id="4e799-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4e799-114">Runtime</span></span>|
