---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614944"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="47946-101">Фокус клавиатуры теперь правильно перемещается на нескольких слоях размещения WinForms и WPF</span><span class="sxs-lookup"><span data-stu-id="47946-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

#### <a name="details"></a><span data-ttu-id="47946-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="47946-102">Details</span></span>

<span data-ttu-id="47946-103">Рассмотрим приложение WPF для размещения элемента управления WinForms, который, в свою очередь, содержит элементы управления WPF.</span><span class="sxs-lookup"><span data-stu-id="47946-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="47946-104">Пользователи не могут перейти из слоя WinForms, если первый или последний элемент управления в этом слое является `System.Windows.Forms.Integration.ElementHost` WPF.</span><span class="sxs-lookup"><span data-stu-id="47946-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF `System.Windows.Forms.Integration.ElementHost`.</span></span> <span data-ttu-id="47946-105">Это изменение устраняет эту проблему: теперь пользователи могут выйти из слоя WinForms. Автоматические приложения, зависящие от фокуса, который никогда не должен выходить из слоя WinForms, могут перестать работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="47946-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47946-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="47946-106">Suggestion</span></span>

<span data-ttu-id="47946-107">Разработчики, желающие использовать это изменение в приложениях для целевой платформы .NET Framework 4.7.2 и более ранних версий, могут задать для следующего набора флагов AppContext значение false, чтобы включить изменение.</span><span class="sxs-lookup"><span data-stu-id="47946-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="47946-108">Для приложений WPF необходимо включить использование всех более ранних усовершенствований специальных возможностей для получения более поздних усовершенствований.</span><span class="sxs-lookup"><span data-stu-id="47946-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="47946-109">Другими словами, оба переключателя, `Switch.UseLegacyAccessibilityFeatures` и `Switch.UseLegacyAccessibilityFeatures.2`, должны быть заданы. Разработчики, которым требуются прежние функции при нацеливании на .NET 4.7.2 и более поздних версий, могут установить для следующего флага AppContext значение true, чтобы отключить изменение.</span><span class="sxs-lookup"><span data-stu-id="47946-109">In other words, both the `Switch.UseLegacyAccessibilityFeatures` and the `Switch.UseLegacyAccessibilityFeatures.2` switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="47946-110">name</span><span class="sxs-lookup"><span data-stu-id="47946-110">Name</span></span>    | <span data-ttu-id="47946-111">Значение</span><span class="sxs-lookup"><span data-stu-id="47946-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47946-112">Область</span><span class="sxs-lookup"><span data-stu-id="47946-112">Scope</span></span>   | <span data-ttu-id="47946-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="47946-113">Edge</span></span>        |
| <span data-ttu-id="47946-114">Version</span><span class="sxs-lookup"><span data-stu-id="47946-114">Version</span></span> | <span data-ttu-id="47946-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="47946-115">4.7.2</span></span>       |
| <span data-ttu-id="47946-116">Type</span><span class="sxs-lookup"><span data-stu-id="47946-116">Type</span></span>    | <span data-ttu-id="47946-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="47946-117">Retargeting</span></span> |
