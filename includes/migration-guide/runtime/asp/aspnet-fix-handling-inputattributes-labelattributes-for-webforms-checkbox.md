---
ms.openlocfilehash: 55a26f1ab27792cbedf3f31b797f37d3f768d51a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496566"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="babb2-101">ASP.NET. Исправление обработки InputAttributes и LabelAttributes для элемента управления "Флажок" в веб-формах</span><span class="sxs-lookup"><span data-stu-id="babb2-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="babb2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="babb2-102">Details</span></span>

<span data-ttu-id="babb2-103">Для приложений, предназначенных для .NET Framework 4.7.2 и более ранних версий, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, добавленные в элемент управления <xref:System.Web.UI.WebControls.CheckBox> веб-форм программными средствами, теряются после обратной передачи.</span><span class="sxs-lookup"><span data-stu-id="babb2-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="babb2-104">Для приложений, предназначенных для .NET Framework 4.8 или более поздних версий, они сохраняются после обратной передачи.</span><span class="sxs-lookup"><span data-stu-id="babb2-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="babb2-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="babb2-105">Suggestion</span></span>

<span data-ttu-id="babb2-106">Для правильного поведения для восстановления атрибутов при обратной передаче задайте <code>targetFrameworkVersion</code> 4.8 или более позднюю версию.</span><span class="sxs-lookup"><span data-stu-id="babb2-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="babb2-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="babb2-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="babb2-108">Если установить значение ниже или не установить никакое значение, сохраняется старое неправильное поведение.</span><span class="sxs-lookup"><span data-stu-id="babb2-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="babb2-109">name</span><span class="sxs-lookup"><span data-stu-id="babb2-109">Name</span></span>    | <span data-ttu-id="babb2-110">Значение</span><span class="sxs-lookup"><span data-stu-id="babb2-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="babb2-111">Область</span><span class="sxs-lookup"><span data-stu-id="babb2-111">Scope</span></span>   |<span data-ttu-id="babb2-112">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="babb2-112">Unknown</span></span>|
|<span data-ttu-id="babb2-113">Version</span><span class="sxs-lookup"><span data-stu-id="babb2-113">Version</span></span>|<span data-ttu-id="babb2-114">4.8</span><span class="sxs-lookup"><span data-stu-id="babb2-114">4.8</span></span>|
|<span data-ttu-id="babb2-115">Type</span><span class="sxs-lookup"><span data-stu-id="babb2-115">Type</span></span>|<span data-ttu-id="babb2-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="babb2-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="babb2-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="babb2-117">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.UI.WebControls.CheckBox`

-->
