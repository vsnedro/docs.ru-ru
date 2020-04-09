---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391186"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="fe325-101">Статические файлы. Тип содержимого CSV изменен на соответствующий стандартам</span><span class="sxs-lookup"><span data-stu-id="fe325-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="fe325-102">В ASP.NET Core 5.0 значение заголовка ответа `Content-Type` по умолчанию, используемое [ПО промежуточного слоя для статических файлов](/aspnet/core/fundamentals/static-files) для *CSV*-файлов, изменилось на соответствующее стандартам значение `text/csv`.</span><span class="sxs-lookup"><span data-stu-id="fe325-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="fe325-103">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span><span class="sxs-lookup"><span data-stu-id="fe325-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fe325-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="fe325-104">Version introduced</span></span>

<span data-ttu-id="fe325-105">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="fe325-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="fe325-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="fe325-106">Old behavior</span></span>

<span data-ttu-id="fe325-107">Использовалось значение `application/octet-stream` заголовка `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="fe325-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="fe325-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="fe325-108">New behavior</span></span>

<span data-ttu-id="fe325-109">Используется значение `text/csv` заголовка `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="fe325-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fe325-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="fe325-110">Reason for change</span></span>

<span data-ttu-id="fe325-111">Соответствие стандарту [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1).</span><span class="sxs-lookup"><span data-stu-id="fe325-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fe325-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="fe325-112">Recommended action</span></span>

<span data-ttu-id="fe325-113">Если это изменение влияет на приложение, можно настроить сопоставление расширения файла с типом MIME.</span><span class="sxs-lookup"><span data-stu-id="fe325-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="fe325-114">Чтобы вернуться к типу MIME `application/octet-stream`, измените вызов метода <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> в `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="fe325-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="fe325-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="fe325-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="fe325-116">Дополнительные сведения о настройке сопоставления см. в разделе [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="fe325-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="fe325-117">Категория</span><span class="sxs-lookup"><span data-stu-id="fe325-117">Category</span></span>

<span data-ttu-id="fe325-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fe325-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fe325-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="fe325-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
