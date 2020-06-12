---
ms.openlocfilehash: b1fb9647091cecb80b9c2f04ec9b6bb156eb39ba
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84466840"
---
### <a name="pubternal-apis-removed"></a><span data-ttu-id="700f5-101">Удалены API-интерфейсы Pubternal</span><span class="sxs-lookup"><span data-stu-id="700f5-101">"Pubternal" APIs removed</span></span>

<span data-ttu-id="700f5-102">Чтобы сохранить порядок в предоставляемой поверхности API платформы ASP.NET Core, большинство типов в пространствах имен `*.Internal` (которые называются API-интерфейсами :::no-loc text="\"pubternal\"":::) стали по-настоящему внутренними.</span><span class="sxs-lookup"><span data-stu-id="700f5-102">To better maintain the public API surface of ASP.NET Core, most of the types in `*.Internal` namespaces (referred to as :::no-loc text="\"pubternal\""::: APIs) have become truly internal.</span></span> <span data-ttu-id="700f5-103">Элементы в этих пространствах имен никогда не предполагалось поддерживать в качестве общедоступных API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="700f5-103">Members in these namespaces were never meant to be supported as public-facing APIs.</span></span> <span data-ttu-id="700f5-104">Для этих API-интерфейсов допускались критические изменения в дополнительных выпусках. Такие изменения применялись часто.</span><span class="sxs-lookup"><span data-stu-id="700f5-104">The APIs could break in minor releases and often did.</span></span> <span data-ttu-id="700f5-105">Любой код, который зависит от этих API-интерфейсов, перестанет работать при обновлении до ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="700f5-105">Code that depends on these APIs breaks when updating to ASP.NET Core 3.0.</span></span>

<span data-ttu-id="700f5-106">Подробную информацию см. на страницах [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) и [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span><span class="sxs-lookup"><span data-stu-id="700f5-106">For more information, see [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) and [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="700f5-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="700f5-107">Version introduced</span></span>

<span data-ttu-id="700f5-108">3.0</span><span class="sxs-lookup"><span data-stu-id="700f5-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="700f5-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="700f5-109">Old behavior</span></span>

<span data-ttu-id="700f5-110">Затронутые API-интерфейсы помечаются модификатором доступа `public` и существуют в пространствах имен `*.Internal`.</span><span class="sxs-lookup"><span data-stu-id="700f5-110">The affected APIs are marked with the `public` access modifier and exist in `*.Internal` namespaces.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="700f5-111">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="700f5-111">New behavior</span></span>

<span data-ttu-id="700f5-112">Затронутые API-интерфейсы помечаются модификатором доступа [internal](/dotnet/csharp/language-reference/keywords/internal) и больше не могут использоваться в коде за пределами этой сборки.</span><span class="sxs-lookup"><span data-stu-id="700f5-112">The affected APIs are marked with the [internal](/dotnet/csharp/language-reference/keywords/internal) access modifier and can no longer be used by code outside that assembly.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="700f5-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="700f5-113">Reason for change</span></span>

<span data-ttu-id="700f5-114">Для этих API-интерфейсов :::no-loc text="\"pubternal\""::: всегда действовали следующие предупреждения:</span><span class="sxs-lookup"><span data-stu-id="700f5-114">The guidance for these :::no-loc text="\"pubternal\""::: APIs was that they:</span></span>

* <span data-ttu-id="700f5-115">Они могут измениться без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="700f5-115">Could change without notice.</span></span>
* <span data-ttu-id="700f5-116">На них не распространяются политики .NET по контролю критических изменений.</span><span class="sxs-lookup"><span data-stu-id="700f5-116">Weren't subject to .NET policies to prevent breaking changes.</span></span>

<span data-ttu-id="700f5-117">Сохранение API-интерфейсов `public` (даже в пространстве имен `*.Internal`) неоднозначно воспринималось пользователями.</span><span class="sxs-lookup"><span data-stu-id="700f5-117">Leaving the APIs `public` (even in the `*.Internal` namespaces) was confusing to customers.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="700f5-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="700f5-118">Recommended action</span></span>

<span data-ttu-id="700f5-119">Прекратите использовать API-интерфейсы :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="700f5-119">Stop using these :::no-loc text="\"pubternal\""::: APIs.</span></span> <span data-ttu-id="700f5-120">Если вы хотите узнать, какие API-интерфейсы лучше использовать вместо них, откройте запрос в репозитории [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="700f5-120">If you have questions about alternate APIs, open an issue in the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) repository.</span></span>

<span data-ttu-id="700f5-121">Для примера давайте рассмотрим приведенный ниже код, который буферизует HTTP-запросы в проекте ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="700f5-121">For example, consider the following HTTP request buffering code in an ASP.NET Core 2.2 project.</span></span> <span data-ttu-id="700f5-122">Методы расширения `EnableRewind` относятся к пространству имен `Microsoft.AspNetCore.Http.Internal`.</span><span class="sxs-lookup"><span data-stu-id="700f5-122">The `EnableRewind` extension method exists in the `Microsoft.AspNetCore.Http.Internal` namespace.</span></span>

```csharp
HttpContext.Request.EnableRewind();
```

<span data-ttu-id="700f5-123">В проекте ASP.NET Core 3.0 замените вызов `EnableRewind` вызовом метода расширения `EnableBuffering`.</span><span class="sxs-lookup"><span data-stu-id="700f5-123">In an ASP.NET Core 3.0 project, replace the `EnableRewind` call with a call to the `EnableBuffering` extension method.</span></span> <span data-ttu-id="700f5-124">Теперь функция буферизации запросов работает так же, как раньше.</span><span class="sxs-lookup"><span data-stu-id="700f5-124">The request buffering feature works as it did in the past.</span></span> <span data-ttu-id="700f5-125">Но теперь `EnableBuffering` вызывает API `internal`.</span><span class="sxs-lookup"><span data-stu-id="700f5-125">`EnableBuffering` calls the now `internal` API.</span></span>

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a><span data-ttu-id="700f5-126">Категория</span><span class="sxs-lookup"><span data-stu-id="700f5-126">Category</span></span>

<span data-ttu-id="700f5-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="700f5-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="700f5-128">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="700f5-128">Affected APIs</span></span>

<span data-ttu-id="700f5-129">Все API-интерфейсы в пространствах имен `Microsoft.AspNetCore.*` и `Microsoft.Extensions.*`, в имени пространства имен которых есть сегмент `Internal`.</span><span class="sxs-lookup"><span data-stu-id="700f5-129">All APIs in the `Microsoft.AspNetCore.*` and `Microsoft.Extensions.*` namespaces that have an `Internal` segment in the namespace name.</span></span> <span data-ttu-id="700f5-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="700f5-130">For example:</span></span>

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
