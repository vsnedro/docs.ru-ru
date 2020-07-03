---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325202"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="30de8-101">IIS. Строки запросов ПО промежуточного слоя UrlRewrite сохраняются</span><span class="sxs-lookup"><span data-stu-id="30de8-101">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="30de8-102">Ошибки в ПО промежуточного слоя IIS UrlRewrite не позволили сохранить строку запроса в правиле перезаписи.</span><span class="sxs-lookup"><span data-stu-id="30de8-102">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="30de8-103">Эта ошибка исправлена, чтобы обеспечить соответствие поведению модуля IIS UrlRewrite.</span><span class="sxs-lookup"><span data-stu-id="30de8-103">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="30de8-104">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="30de8-104">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="30de8-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30de8-105">Version introduced</span></span>

<span data-ttu-id="30de8-106">ASP.NET Core 5.0 (предварительная версия 7)</span><span class="sxs-lookup"><span data-stu-id="30de8-106">ASP.NET Core 5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="30de8-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="30de8-107">Old behavior</span></span>

<span data-ttu-id="30de8-108">Рассмотрим следующее правило перезаписи.</span><span class="sxs-lookup"><span data-stu-id="30de8-108">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="30de8-109">Предыдущее правило не присоединяет строку запроса.</span><span class="sxs-lookup"><span data-stu-id="30de8-109">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="30de8-110">Универсальный код ресурса (URI), такой как `/about?id=1`, перенаправляет в `/contact` вместо `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="30de8-110">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="30de8-111">По умолчанию атрибут `appendQueryString` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="30de8-111">The `appendQueryString` attribute defaults to `true` as well.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="30de8-112">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="30de8-112">New behavior</span></span>

<span data-ttu-id="30de8-113">Строка запроса сохраняется.</span><span class="sxs-lookup"><span data-stu-id="30de8-113">The query string is preserved.</span></span> <span data-ttu-id="30de8-114">Код URI из примера в разделе [Старое поведение](#old-behavior) будет иметь значение `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="30de8-114">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="30de8-115">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="30de8-115">Reason for change</span></span>

<span data-ttu-id="30de8-116">Старое поведение не соответствовало поведению модуля IIS UrlRewrite.</span><span class="sxs-lookup"><span data-stu-id="30de8-116">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="30de8-117">Для поддержки переноса между ПО промежуточного слоя и модулем важно обеспечить согласованное поведение.</span><span class="sxs-lookup"><span data-stu-id="30de8-117">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="30de8-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="30de8-118">Recommended action</span></span>

<span data-ttu-id="30de8-119">Если удаление строки запроса является предпочтительным поведением, следует установить для элемента `action` значение `appendQueryString="false"`.</span><span class="sxs-lookup"><span data-stu-id="30de8-119">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

#### <a name="category"></a><span data-ttu-id="30de8-120">Категория</span><span class="sxs-lookup"><span data-stu-id="30de8-120">Category</span></span>

<span data-ttu-id="30de8-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30de8-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="30de8-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="30de8-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
