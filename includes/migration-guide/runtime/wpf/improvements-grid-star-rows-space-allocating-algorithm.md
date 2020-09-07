---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496760"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="4dfc7-101">Усовершенствования алгоритма выделения пространства для строк со звездами в сетке</span><span class="sxs-lookup"><span data-stu-id="4dfc7-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="4dfc7-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4dfc7-102">Details</span></span>

<span data-ttu-id="4dfc7-103">Исправлена ошибка в [алгоритме выделения размеров для ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) в <xref:System.Windows.Controls.Grid>, представленном в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="4dfc7-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="4dfc7-104">В некоторых случаях, например в сетке с <code>Height=&quot;Auto&quot;</code>, которая содержит пустые строки, строки были расположены в неправильном положении, возможно, даже за пределами сетки.</span><span class="sxs-lookup"><span data-stu-id="4dfc7-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4dfc7-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="4dfc7-105">Suggestion</span></span>

<span data-ttu-id="4dfc7-106">Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4dfc7-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="4dfc7-107">name</span><span class="sxs-lookup"><span data-stu-id="4dfc7-107">Name</span></span>    | <span data-ttu-id="4dfc7-108">Значение</span><span class="sxs-lookup"><span data-stu-id="4dfc7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4dfc7-109">Область</span><span class="sxs-lookup"><span data-stu-id="4dfc7-109">Scope</span></span>   |<span data-ttu-id="4dfc7-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="4dfc7-110">Major</span></span>|
|<span data-ttu-id="4dfc7-111">Version</span><span class="sxs-lookup"><span data-stu-id="4dfc7-111">Version</span></span>|<span data-ttu-id="4dfc7-112">4.8</span><span class="sxs-lookup"><span data-stu-id="4dfc7-112">4.8</span></span>|
|<span data-ttu-id="4dfc7-113">Type</span><span class="sxs-lookup"><span data-stu-id="4dfc7-113">Type</span></span>|<span data-ttu-id="4dfc7-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4dfc7-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4dfc7-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4dfc7-115">Affected APIs</span></span>

<span data-ttu-id="4dfc7-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="4dfc7-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
