---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615645"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="76f22-101">HtmlTextWriter неправильно отображает элемент `<br/>`</span><span class="sxs-lookup"><span data-stu-id="76f22-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

#### <a name="details"></a><span data-ttu-id="76f22-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="76f22-102">Details</span></span>

<span data-ttu-id="76f22-103">Начиная с .NET Framework 4.6, при вызове <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> и <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> с элементом `<BR />` правильно вставляется только один `<BR />` (вместо двух).</span><span class="sxs-lookup"><span data-stu-id="76f22-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a `<BR />` element will correctly insert only one `<BR />` (instead of two)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="76f22-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="76f22-104">Suggestion</span></span>

<span data-ttu-id="76f22-105">Если приложение зависит от дополнительного тега `<BR />`, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> следует вызвать второй раз.</span><span class="sxs-lookup"><span data-stu-id="76f22-105">If an app depended on the extra `<BR />` tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="76f22-106">Обратите внимание, что это изменение поведения влияет только на приложения, предназначенные для .NET Framework 4.6 или более поздних версий, поэтому другим вариантом является нацеливание на предыдущую версию платформы .NET Framework для получения старого поведения.</span><span class="sxs-lookup"><span data-stu-id="76f22-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>

| <span data-ttu-id="76f22-107">name</span><span class="sxs-lookup"><span data-stu-id="76f22-107">Name</span></span>    | <span data-ttu-id="76f22-108">Значение</span><span class="sxs-lookup"><span data-stu-id="76f22-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="76f22-109">Область</span><span class="sxs-lookup"><span data-stu-id="76f22-109">Scope</span></span>   | <span data-ttu-id="76f22-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="76f22-110">Edge</span></span>        |
| <span data-ttu-id="76f22-111">Version</span><span class="sxs-lookup"><span data-stu-id="76f22-111">Version</span></span> | <span data-ttu-id="76f22-112">4.6</span><span class="sxs-lookup"><span data-stu-id="76f22-112">4.6</span></span>         |
| <span data-ttu-id="76f22-113">Type</span><span class="sxs-lookup"><span data-stu-id="76f22-113">Type</span></span>    | <span data-ttu-id="76f22-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="76f22-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="76f22-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="76f22-115">Affected APIs</span></span>

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
