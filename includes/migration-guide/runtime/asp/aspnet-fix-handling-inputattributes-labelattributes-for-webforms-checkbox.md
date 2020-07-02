---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622075"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="c0e58-101">ASP.NET. Исправление обработки InputAttributes и LabelAttributes для элемента управления "Флажок" в веб-формах</span><span class="sxs-lookup"><span data-stu-id="c0e58-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="c0e58-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c0e58-102">Details</span></span>

<span data-ttu-id="c0e58-103">Для приложений, предназначенных для .NET Framework 4.7.2 и более ранних версий, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, добавленные в элемент управления <xref:System.Web.UI.WebControls.CheckBox> веб-форм программными средствами, теряются после обратной передачи.</span><span class="sxs-lookup"><span data-stu-id="c0e58-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="c0e58-104">Для приложений, предназначенных для .NET Framework 4.8 или более поздних версий, они сохраняются после обратной передачи.</span><span class="sxs-lookup"><span data-stu-id="c0e58-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c0e58-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c0e58-105">Suggestion</span></span>

<span data-ttu-id="c0e58-106">Для правильного поведения для восстановления атрибутов при обратной передаче задайте <code>targetFrameworkVersion</code> 4.8 или более позднюю версию.</span><span class="sxs-lookup"><span data-stu-id="c0e58-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="c0e58-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="c0e58-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="c0e58-108">Если установить значение ниже или не установить никакое значение, сохраняется старое неправильное поведение.</span><span class="sxs-lookup"><span data-stu-id="c0e58-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="c0e58-109">name</span><span class="sxs-lookup"><span data-stu-id="c0e58-109">Name</span></span>    | <span data-ttu-id="c0e58-110">Значение</span><span class="sxs-lookup"><span data-stu-id="c0e58-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c0e58-111">Область</span><span class="sxs-lookup"><span data-stu-id="c0e58-111">Scope</span></span>   |<span data-ttu-id="c0e58-112">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="c0e58-112">Unknown</span></span>|
|<span data-ttu-id="c0e58-113">Version</span><span class="sxs-lookup"><span data-stu-id="c0e58-113">Version</span></span>|<span data-ttu-id="c0e58-114">4.8</span><span class="sxs-lookup"><span data-stu-id="c0e58-114">4.8</span></span>|
|<span data-ttu-id="c0e58-115">Type</span><span class="sxs-lookup"><span data-stu-id="c0e58-115">Type</span></span>|<span data-ttu-id="c0e58-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c0e58-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c0e58-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c0e58-117">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
