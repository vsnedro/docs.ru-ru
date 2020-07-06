---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614937"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="515d8-101">Событие SelectionChanged и свойство SelectedValue селектора</span><span class="sxs-lookup"><span data-stu-id="515d8-101">Selector SelectionChanged event and SelectedValue property</span></span>

#### <a name="details"></a><span data-ttu-id="515d8-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="515d8-102">Details</span></span>

<span data-ttu-id="515d8-103">Начиная с .NET Framework 4.7.1 <xref:System.Windows.Controls.Primitives.Selector> всегда обновляет значение своего свойства <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> до порождения события <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> при изменении его выбора.</span><span class="sxs-lookup"><span data-stu-id="515d8-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="515d8-104">Это позволяет согласовать свойство SelectedValue с другими свойствами выбора (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> и <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), которые изменяются перед порождением события.</span><span class="sxs-lookup"><span data-stu-id="515d8-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="515d8-105">В .NET Framework 4.7 и более ранних версий изменение SelectedValue в большинстве случаев происходило до события, но оно выполнялось после события, если изменение выбора было вызвано изменением свойства <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="515d8-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="515d8-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="515d8-106">Suggestion</span></span>

<span data-ttu-id="515d8-107">В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, данное изменение можно отключить и использовать устаревшее поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="515d8-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="515d8-108">В приложениях, предназначенных для .NET Framework 4.7 или более ранней версии, но работающих на платформе .NET Framework 4.7.1 или более поздней версии, можно включить новое поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="515d8-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="515d8-109">name</span><span class="sxs-lookup"><span data-stu-id="515d8-109">Name</span></span>    | <span data-ttu-id="515d8-110">Значение</span><span class="sxs-lookup"><span data-stu-id="515d8-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="515d8-111">Область</span><span class="sxs-lookup"><span data-stu-id="515d8-111">Scope</span></span>   | <span data-ttu-id="515d8-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="515d8-112">Minor</span></span>       |
| <span data-ttu-id="515d8-113">Версия</span><span class="sxs-lookup"><span data-stu-id="515d8-113">Version</span></span> | <span data-ttu-id="515d8-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="515d8-114">4.7.1</span></span>       |
| <span data-ttu-id="515d8-115">Type</span><span class="sxs-lookup"><span data-stu-id="515d8-115">Type</span></span>    | <span data-ttu-id="515d8-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="515d8-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="515d8-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="515d8-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
