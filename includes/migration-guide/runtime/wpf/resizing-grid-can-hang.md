---
ms.openlocfilehash: 8dc1b4d94d01813a8124d1340b50fa78a9b157f8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496264"
---
### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="56cf8-101">Изменение размеров сетки может привести к зависанию</span><span class="sxs-lookup"><span data-stu-id="56cf8-101">Resizing a Grid can hang</span></span>

#### <a name="details"></a><span data-ttu-id="56cf8-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="56cf8-102">Details</span></span>

<span data-ttu-id="56cf8-103">При изменении макета <code>T:System.Windows.Controls.Grid</code> в следующих обстоятельствах может возникать бесконечный цикл:</span><span class="sxs-lookup"><span data-stu-id="56cf8-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="56cf8-104">Определения строк содержат два атрибута \*-rows, которые объявляют значения MinHeight и MaxHeight.</span><span class="sxs-lookup"><span data-stu-id="56cf8-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="56cf8-105">Содержимое \*-rows не превышает ограничение, устанавливаемое соответствующим значением MaxHeight.</span><span class="sxs-lookup"><span data-stu-id="56cf8-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="56cf8-106">Первое значение MinHeight (плюс любые другие фиксированные или автоматические строки) превышает доступную высоту сетки.</span><span class="sxs-lookup"><span data-stu-id="56cf8-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="56cf8-107">Приложение предназначено для .NET Framework 4.7 или использует алгоритм выделения версии 4.7, включенный с помощью параметра <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>.</span><span class="sxs-lookup"><span data-stu-id="56cf8-107">The app targets .NET Framework 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="56cf8-108">Кроме того, цикл может возникать при наличии более двух строк или в аналогичных случаях для столбцов.</span><span class="sxs-lookup"><span data-stu-id="56cf8-108">The loop would also happen with more than two rows, or in the analogous case for columns.</span></span> <span data-ttu-id="56cf8-109">Проблема устранена в .Net Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="56cf8-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="56cf8-110">Предложение</span><span class="sxs-lookup"><span data-stu-id="56cf8-110">Suggestion</span></span>

<span data-ttu-id="56cf8-111">Выполните обновление до .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="56cf8-111">Upgrade to .NET Framework 4.7.1.</span></span>  <span data-ttu-id="56cf8-112">Кроме того, если вам не требуется алгоритм выделения версии 4.7, вы можете использовать следующий параметр конфигурации:</span><span class="sxs-lookup"><span data-stu-id="56cf8-112">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="56cf8-113">Имя</span><span class="sxs-lookup"><span data-stu-id="56cf8-113">Name</span></span>    | <span data-ttu-id="56cf8-114">Значение</span><span class="sxs-lookup"><span data-stu-id="56cf8-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="56cf8-115">Область</span><span class="sxs-lookup"><span data-stu-id="56cf8-115">Scope</span></span>   |<span data-ttu-id="56cf8-116">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="56cf8-116">Edge</span></span>|
|<span data-ttu-id="56cf8-117">Version</span><span class="sxs-lookup"><span data-stu-id="56cf8-117">Version</span></span>|<span data-ttu-id="56cf8-118">4.7</span><span class="sxs-lookup"><span data-stu-id="56cf8-118">4.7</span></span>|
|<span data-ttu-id="56cf8-119">Type</span><span class="sxs-lookup"><span data-stu-id="56cf8-119">Type</span></span>|<span data-ttu-id="56cf8-120">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="56cf8-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="56cf8-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="56cf8-121">Affected APIs</span></span>

<span data-ttu-id="56cf8-122">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="56cf8-122">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
