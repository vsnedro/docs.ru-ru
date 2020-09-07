---
ms.openlocfilehash: afbf34710c75d0f0586ddfdb2e7937d8d76d5399
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496948"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="f3f0b-101">ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута</span><span class="sxs-lookup"><span data-stu-id="f3f0b-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="f3f0b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f3f0b-102">Details</span></span>

<span data-ttu-id="f3f0b-103">Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута.</span><span class="sxs-lookup"><span data-stu-id="f3f0b-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="f3f0b-104">Таким образом, в то время как <code>/controller/action/some data</code> ранее соответствовал маршруту <code>/controller/action/{data}</code> и предоставлял <code>some data</code> в качестве параметра данных, теперь он будет предоставлять <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="f3f0b-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f3f0b-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="f3f0b-105">Suggestion</span></span>

<span data-ttu-id="f3f0b-106">Код должен быть обновлен для неэкранирования строковых параметров из маршрута.</span><span class="sxs-lookup"><span data-stu-id="f3f0b-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="f3f0b-107">Если необходим исходный URI, доступ к нему можно получить с помощью API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="f3f0b-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="f3f0b-108">name</span><span class="sxs-lookup"><span data-stu-id="f3f0b-108">Name</span></span>    | <span data-ttu-id="f3f0b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f3f0b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f3f0b-110">Область</span><span class="sxs-lookup"><span data-stu-id="f3f0b-110">Scope</span></span>   |<span data-ttu-id="f3f0b-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f3f0b-111">Minor</span></span>|
|<span data-ttu-id="f3f0b-112">Version</span><span class="sxs-lookup"><span data-stu-id="f3f0b-112">Version</span></span>|<span data-ttu-id="f3f0b-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f3f0b-113">4.5.2</span></span>|
|<span data-ttu-id="f3f0b-114">Type</span><span class="sxs-lookup"><span data-stu-id="f3f0b-114">Type</span></span>|<span data-ttu-id="f3f0b-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f3f0b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f3f0b-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f3f0b-116">Affected APIs</span></span>

- <xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)>

<!--

#### Affected APIs

- `M:System.Web.Mvc.RouteAttribute.#ctor(System.String)`

-->
