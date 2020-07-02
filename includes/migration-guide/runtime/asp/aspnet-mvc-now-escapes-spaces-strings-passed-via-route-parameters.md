---
ms.openlocfilehash: c53fe57f3278741a927a2f00b11af6e26dafce66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620148"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="e3136-101">ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута</span><span class="sxs-lookup"><span data-stu-id="e3136-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="e3136-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e3136-102">Details</span></span>

<span data-ttu-id="e3136-103">Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута.</span><span class="sxs-lookup"><span data-stu-id="e3136-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="e3136-104">Таким образом, в то время как <code>/controller/action/some data</code> ранее соответствовал маршруту <code>/controller/action/{data}</code> и предоставлял <code>some data</code> в качестве параметра данных, теперь он будет предоставлять <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="e3136-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e3136-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e3136-105">Suggestion</span></span>

<span data-ttu-id="e3136-106">Код должен быть обновлен для неэкранирования строковых параметров из маршрута.</span><span class="sxs-lookup"><span data-stu-id="e3136-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="e3136-107">Если необходим исходный URI, доступ к нему можно получить с помощью API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="e3136-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="e3136-108">name</span><span class="sxs-lookup"><span data-stu-id="e3136-108">Name</span></span>    | <span data-ttu-id="e3136-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e3136-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e3136-110">Область</span><span class="sxs-lookup"><span data-stu-id="e3136-110">Scope</span></span>   |<span data-ttu-id="e3136-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e3136-111">Minor</span></span>|
|<span data-ttu-id="e3136-112">Version</span><span class="sxs-lookup"><span data-stu-id="e3136-112">Version</span></span>|<span data-ttu-id="e3136-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="e3136-113">4.5.2</span></span>|
|<span data-ttu-id="e3136-114">Type</span><span class="sxs-lookup"><span data-stu-id="e3136-114">Type</span></span>|<span data-ttu-id="e3136-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e3136-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e3136-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e3136-116">Affected APIs</span></span>

-<xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
