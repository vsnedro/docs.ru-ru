---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507102"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="7cb03-101">HTTP. Типы Kestrel и IIS BadHttpRequestException, помеченные как устаревшие и замененные</span><span class="sxs-lookup"><span data-stu-id="7cb03-101">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="7cb03-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` и `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` были помечены как устаревшие и изменены, чтобы быть производными от `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="7cb03-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="7cb03-103">Серверы Kestrel и IIS по-прежнему выдают старые типы исключений для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="7cb03-103">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="7cb03-104">Устаревшие типы будут удалены в будущем выпуске.</span><span class="sxs-lookup"><span data-stu-id="7cb03-104">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="7cb03-105">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="7cb03-105">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7cb03-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="7cb03-106">Version introduced</span></span>

<span data-ttu-id="7cb03-107">5.0, предварительная версия 4</span><span class="sxs-lookup"><span data-stu-id="7cb03-107">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7cb03-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="7cb03-108">Old behavior</span></span>

<span data-ttu-id="7cb03-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` и `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` являются производными от <xref:System.IO.IOException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7cb03-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7cb03-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="7cb03-110">New behavior</span></span>

<span data-ttu-id="7cb03-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` и `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="7cb03-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="7cb03-112">Типы являются производными от `Microsoft.AspNetCore.Http.BadHttpRequestException`, который является производным от `System.IO.IOException`.</span><span class="sxs-lookup"><span data-stu-id="7cb03-112">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7cb03-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="7cb03-113">Reason for change</span></span>

<span data-ttu-id="7cb03-114">Изменение было внесено в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="7cb03-114">The change was made to:</span></span>

* <span data-ttu-id="7cb03-115">Консолидация повторяющихся типов.</span><span class="sxs-lookup"><span data-stu-id="7cb03-115">Consolidate duplicate types.</span></span>
* <span data-ttu-id="7cb03-116">Унификация поведения различных серверных реализаций.</span><span class="sxs-lookup"><span data-stu-id="7cb03-116">Unify behavior across server implementations.</span></span>

<span data-ttu-id="7cb03-117">Теперь приложение может перехватывать базовое исключение `Microsoft.AspNetCore.Http.BadHttpRequestException` при использовании Kestrel или IIS.</span><span class="sxs-lookup"><span data-stu-id="7cb03-117">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7cb03-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="7cb03-118">Recommended action</span></span>

<span data-ttu-id="7cb03-119">Замените `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` и `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` на `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="7cb03-119">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

#### <a name="category"></a><span data-ttu-id="7cb03-120">Категория</span><span class="sxs-lookup"><span data-stu-id="7cb03-120">Category</span></span>

<span data-ttu-id="7cb03-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7cb03-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7cb03-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7cb03-122">Affected APIs</span></span>

- [<span data-ttu-id="7cb03-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="7cb03-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="7cb03-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="7cb03-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
