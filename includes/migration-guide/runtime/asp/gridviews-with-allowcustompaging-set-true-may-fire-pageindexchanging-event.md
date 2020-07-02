---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620136"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="d4434-101">Если в GridViews для свойства AllowCustomPaging установлено значение true, может возникать событие PageIndexChanging при выходе из последней страницы представления</span><span class="sxs-lookup"><span data-stu-id="d4434-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="d4434-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d4434-102">Details</span></span>

<span data-ttu-id="d4434-103">В результате ошибки в .NET Framework 4.5 иногда событие <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> не срабатывает для <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> со свойством <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d4434-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d4434-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="d4434-104">Suggestion</span></span>

<span data-ttu-id="d4434-105">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4434-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="d4434-106">Чтобы обойти эту проблему, приложение может иметь явный BindGrid в любом <code>Page_Load</code>, которое вызывает эти условия (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> находится на последней странице, а Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> отличается от <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="d4434-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="d4434-107">Кроме того, приложение можно изменить, чтобы разрешить разбивку на страницы (вместо пользовательского разбиения по страницам), поскольку в этом случае проблемы не возникают.</span><span class="sxs-lookup"><span data-stu-id="d4434-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="d4434-108">name</span><span class="sxs-lookup"><span data-stu-id="d4434-108">Name</span></span>    | <span data-ttu-id="d4434-109">Значение</span><span class="sxs-lookup"><span data-stu-id="d4434-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d4434-110">Область</span><span class="sxs-lookup"><span data-stu-id="d4434-110">Scope</span></span>   |<span data-ttu-id="d4434-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="d4434-111">Minor</span></span>|
|<span data-ttu-id="d4434-112">Version</span><span class="sxs-lookup"><span data-stu-id="d4434-112">Version</span></span>|<span data-ttu-id="d4434-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d4434-113">4.5</span></span>|
|<span data-ttu-id="d4434-114">Type</span><span class="sxs-lookup"><span data-stu-id="d4434-114">Type</span></span>|<span data-ttu-id="d4434-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d4434-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d4434-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d4434-116">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
