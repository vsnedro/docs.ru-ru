---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615773"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="14ff2-101">Изменились параметры округления полей макета WPF</span><span class="sxs-lookup"><span data-stu-id="14ff2-101">WPF layout rounding of margins has changed</span></span>

#### <a name="details"></a><span data-ttu-id="14ff2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="14ff2-102">Details</span></span>

<span data-ttu-id="14ff2-103">Способ округления полей, а также их границ и фона, изменен.</span><span class="sxs-lookup"><span data-stu-id="14ff2-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="14ff2-104">В результате этого изменения:</span><span class="sxs-lookup"><span data-stu-id="14ff2-104">As a result of this change:</span></span>

- <span data-ttu-id="14ff2-105">ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;</span><span class="sxs-lookup"><span data-stu-id="14ff2-105">The width or height of elements may grow or shrink by at most one pixel.</span></span>
- <span data-ttu-id="14ff2-106">расположение объекта может измениться максимум на один пиксель;</span><span class="sxs-lookup"><span data-stu-id="14ff2-106">The placement of an object can move by at most one pixel.</span></span>
- <span data-ttu-id="14ff2-107">выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.</span><span class="sxs-lookup"><span data-stu-id="14ff2-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>
<span data-ttu-id="14ff2-108">По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="14ff2-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="14ff2-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="14ff2-109">Suggestion</span></span>

<span data-ttu-id="14ff2-110">Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="14ff2-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

<span data-ttu-id="14ff2-111">Для приложений, предназначенных для .NET Framework 4.6, в которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="14ff2-111">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| <span data-ttu-id="14ff2-112">name</span><span class="sxs-lookup"><span data-stu-id="14ff2-112">Name</span></span>    | <span data-ttu-id="14ff2-113">Значение</span><span class="sxs-lookup"><span data-stu-id="14ff2-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="14ff2-114">Область</span><span class="sxs-lookup"><span data-stu-id="14ff2-114">Scope</span></span>   | <span data-ttu-id="14ff2-115">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="14ff2-115">Minor</span></span>       |
| <span data-ttu-id="14ff2-116">Version</span><span class="sxs-lookup"><span data-stu-id="14ff2-116">Version</span></span> | <span data-ttu-id="14ff2-117">4.6</span><span class="sxs-lookup"><span data-stu-id="14ff2-117">4.6</span></span>         |
| <span data-ttu-id="14ff2-118">Type</span><span class="sxs-lookup"><span data-stu-id="14ff2-118">Type</span></span>    | <span data-ttu-id="14ff2-119">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="14ff2-119">Retargeting</span></span> |
