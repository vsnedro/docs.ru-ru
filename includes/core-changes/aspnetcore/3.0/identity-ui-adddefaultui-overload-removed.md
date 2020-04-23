---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637201"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="d8d4a-101">Удостоверение: перегрузка метода AddDefaultUI устранена</span><span class="sxs-lookup"><span data-stu-id="d8d4a-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="d8d4a-102">Начиная с ASP.NET Core 3.0, перегрузка метода [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) больше не существует.</span><span class="sxs-lookup"><span data-stu-id="d8d4a-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d8d4a-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d8d4a-103">Version introduced</span></span>

<span data-ttu-id="d8d4a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d8d4a-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d8d4a-105">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="d8d4a-105">Reason for change</span></span>

<span data-ttu-id="d8d4a-106">Это изменение было результатом внедрения функции статических веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d8d4a-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d8d4a-107">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="d8d4a-107">Recommended action</span></span>

<span data-ttu-id="d8d4a-108">Вызывайте <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> вместо перегрузки, принимающей два аргумента.</span><span class="sxs-lookup"><span data-stu-id="d8d4a-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="d8d4a-109">Если вы используете Bootstrap 3, добавьте следующую строку в элемент `<PropertyGroup>` в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="d8d4a-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="d8d4a-110">Категория</span><span class="sxs-lookup"><span data-stu-id="d8d4a-110">Category</span></span>

<span data-ttu-id="d8d4a-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d8d4a-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d8d4a-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d8d4a-112">Affected APIs</span></span>

[<span data-ttu-id="d8d4a-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="d8d4a-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
