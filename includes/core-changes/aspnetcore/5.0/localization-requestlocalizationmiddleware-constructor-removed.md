---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309167"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="25d57-101">Локализация. Из ПО промежуточного слоя локализации запроса удален устаревший конструктор</span><span class="sxs-lookup"><span data-stu-id="25d57-101">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="25d57-102">Конструктор <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware>, в котором отсутствует параметр <xref:Microsoft.Extensions.Logging.ILoggerFactory>, был помечен [в этой фиксации](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0) как устаревший.</span><span class="sxs-lookup"><span data-stu-id="25d57-102">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="25d57-103">В ASP.NET Core 5.0 устаревший конструктор был удален.</span><span class="sxs-lookup"><span data-stu-id="25d57-103">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="25d57-104">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="25d57-104">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="25d57-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="25d57-105">Version introduced</span></span>

<span data-ttu-id="25d57-106">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="25d57-106">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="25d57-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="25d57-107">Old behavior</span></span>

<span data-ttu-id="25d57-108">Присутствует устаревший конструктор `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)`.</span><span class="sxs-lookup"><span data-stu-id="25d57-108">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="25d57-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="25d57-109">New behavior</span></span>

<span data-ttu-id="25d57-110">Устаревший конструктор `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` удален.</span><span class="sxs-lookup"><span data-stu-id="25d57-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="25d57-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="25d57-111">Reason for change</span></span>

<span data-ttu-id="25d57-112">Это изменение гарантирует, что ПО промежуточного слоя локализации запроса будет всегда иметь доступ к средству ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="25d57-112">This change ensures that the request localization middleware always has access to a logger.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="25d57-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="25d57-113">Recommended action</span></span>

<span data-ttu-id="25d57-114">При создании экземпляра `RequestLocalizationMiddleware` вручную передайте экземпляр `ILoggerFactory` в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="25d57-114">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="25d57-115">Если допустимый экземпляр `ILoggerFactory` недоступен в этом контексте, попробуйте передать конструктор ПО промежуточного слоя экземпляру <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory>.</span><span class="sxs-lookup"><span data-stu-id="25d57-115">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

#### <a name="category"></a><span data-ttu-id="25d57-116">Категория</span><span class="sxs-lookup"><span data-stu-id="25d57-116">Category</span></span>

<span data-ttu-id="25d57-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="25d57-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="25d57-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="25d57-118">Affected APIs</span></span>

[<span data-ttu-id="25d57-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="25d57-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
