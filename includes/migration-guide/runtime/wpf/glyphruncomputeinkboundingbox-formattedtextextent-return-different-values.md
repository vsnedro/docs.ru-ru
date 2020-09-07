---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497785"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="b246b-101">Начиная с .NET Framework 4.5 GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent возвращают разные значения</span><span class="sxs-lookup"><span data-stu-id="b246b-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="b246b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b246b-102">Details</span></span>

<span data-ttu-id="b246b-103">В .NET Framework 4.5 были усовершенствованы <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> и <xref:System.Windows.Media.FormattedText.Extent> для решения проблем, когда в некоторых случаях в .NET Framework 4.0 прямоугольники были слишком малы для содержащихся глифов.</span><span class="sxs-lookup"><span data-stu-id="b246b-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="b246b-104">В результате, начиная с .NET Framework 4.5, некоторые ограничивающие прямоугольники будут иметь больший размер, что приведет к незначительным отличиям в макете пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b246b-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b246b-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="b246b-105">Suggestion</span></span>

<span data-ttu-id="b246b-106">Имейте в виду, что размеры некоторых ограничивающих прямоугольников глифов увеличены.</span><span class="sxs-lookup"><span data-stu-id="b246b-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="b246b-107">Эти изменения обычно улучшают представление и проверку нахождения в поле. Прежнее (до .NET 4.5) поведение можно восстановить, добавив следующую запись в файл app.config.</span><span class="sxs-lookup"><span data-stu-id="b246b-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b246b-108">name</span><span class="sxs-lookup"><span data-stu-id="b246b-108">Name</span></span>    | <span data-ttu-id="b246b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="b246b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b246b-110">Область</span><span class="sxs-lookup"><span data-stu-id="b246b-110">Scope</span></span>   |<span data-ttu-id="b246b-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="b246b-111">Edge</span></span>|
|<span data-ttu-id="b246b-112">Version</span><span class="sxs-lookup"><span data-stu-id="b246b-112">Version</span></span>|<span data-ttu-id="b246b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b246b-113">4.5</span></span>|
|<span data-ttu-id="b246b-114">Type</span><span class="sxs-lookup"><span data-stu-id="b246b-114">Type</span></span>|<span data-ttu-id="b246b-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b246b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b246b-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b246b-116">Affected APIs</span></span>

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
