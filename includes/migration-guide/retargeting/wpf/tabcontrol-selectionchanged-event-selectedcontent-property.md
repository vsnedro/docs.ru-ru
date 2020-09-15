---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614951"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="440c1-101">Событие SelectionChanged и свойство SelectedContent для TabControl</span><span class="sxs-lookup"><span data-stu-id="440c1-101">TabControl SelectionChanged event and SelectedContent property</span></span>

#### <a name="details"></a><span data-ttu-id="440c1-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="440c1-102">Details</span></span>

<span data-ttu-id="440c1-103">Начиная с версии .NET Framework 4.7.1, <xref:System.Windows.Controls.TabControl> обновляет значение своего свойства <xref:System.Windows.Controls.TabControl.SelectedContent> до того, как создать событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>, даже в случае изменения выделения. В .NET Framework 4.7 и более ранних версий обновление SelectedContent происходило после создания события.</span><span class="sxs-lookup"><span data-stu-id="440c1-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="440c1-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="440c1-104">Suggestion</span></span>

<span data-ttu-id="440c1-105">В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, данное изменение можно отключить и использовать устаревшее поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="440c1-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="440c1-106">В приложениях, предназначенных для .NET Framework 4.7 или более ранней версии, но работающих на платформе .NET Framework 4.7.1 или более поздней версии, можно включить новое поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="440c1-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="440c1-107">name</span><span class="sxs-lookup"><span data-stu-id="440c1-107">Name</span></span>    | <span data-ttu-id="440c1-108">Значение</span><span class="sxs-lookup"><span data-stu-id="440c1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="440c1-109">Область</span><span class="sxs-lookup"><span data-stu-id="440c1-109">Scope</span></span>   | <span data-ttu-id="440c1-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="440c1-110">Minor</span></span>       |
| <span data-ttu-id="440c1-111">Версия</span><span class="sxs-lookup"><span data-stu-id="440c1-111">Version</span></span> | <span data-ttu-id="440c1-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="440c1-112">4.7.1</span></span>       |
| <span data-ttu-id="440c1-113">Type</span><span class="sxs-lookup"><span data-stu-id="440c1-113">Type</span></span>    | <span data-ttu-id="440c1-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="440c1-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="440c1-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="440c1-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
