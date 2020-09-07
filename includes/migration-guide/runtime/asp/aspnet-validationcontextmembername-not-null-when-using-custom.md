---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496867"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="1f582-101">ASP.NET ValidationContext.MemberName не имеет значения NULL при использовании пользовательского DataAnnotations.ValidationAttribute</span><span class="sxs-lookup"><span data-stu-id="1f582-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

#### <a name="details"></a><span data-ttu-id="1f582-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1f582-102">Details</span></span>

<span data-ttu-id="1f582-103">В .NET Framework 4.7.2 и более ранних версий при использовании пользовательского <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> свойство <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> возвращает `null`.</span><span class="sxs-lookup"><span data-stu-id="1f582-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns `null`.</span></span> <span data-ttu-id="1f582-104">В версии .NET Framework 4.8 до обновления October 2019 возвращает имя элемента.</span><span class="sxs-lookup"><span data-stu-id="1f582-104">In .NET Framework 4.8 version prior to the October 2019 update, it returns the member name.</span></span> <span data-ttu-id="1f582-105">Начиная с версии [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) для .NET Framework 4.8 возвращает `null` по умолчанию, но при этом сохраняется возможность вернуть имя элемента.</span><span class="sxs-lookup"><span data-stu-id="1f582-105">Starting with [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8, it returns `null` by default, but you can opt in to return the member name instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1f582-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="1f582-106">Suggestion</span></span>

<span data-ttu-id="1f582-107">Добавьте следующий параметр в файл *web.config* для свойства, чтобы вернуть имя элемента в [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) для .NET Framework 4.8 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="1f582-107">Add the following setting to your *web.config* file for the property to return the member name in [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8 and later versions:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="1f582-108">В версии .NET Framework 4.8 до обновления October 2019, добавление этого параметра в файл *web.config* восстанавливает предыдущее поведение, а свойство возвращает `null`.</span><span class="sxs-lookup"><span data-stu-id="1f582-108">In .NET Framework 4.8 version prior to the October 2019 update,  adding this to your *web.config* file restores the previous behavior and the property returns `null`.</span></span>

| <span data-ttu-id="1f582-109">name</span><span class="sxs-lookup"><span data-stu-id="1f582-109">Name</span></span>    | <span data-ttu-id="1f582-110">Значение</span><span class="sxs-lookup"><span data-stu-id="1f582-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1f582-111">Область</span><span class="sxs-lookup"><span data-stu-id="1f582-111">Scope</span></span>   |<span data-ttu-id="1f582-112">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="1f582-112">Unknown</span></span>|
|<span data-ttu-id="1f582-113">Version</span><span class="sxs-lookup"><span data-stu-id="1f582-113">Version</span></span>|<span data-ttu-id="1f582-114">4.8</span><span class="sxs-lookup"><span data-stu-id="1f582-114">4.8</span></span>|
|<span data-ttu-id="1f582-115">Type</span><span class="sxs-lookup"><span data-stu-id="1f582-115">Type</span></span>|<span data-ttu-id="1f582-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="1f582-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1f582-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1f582-117">Affected APIs</span></span>

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
