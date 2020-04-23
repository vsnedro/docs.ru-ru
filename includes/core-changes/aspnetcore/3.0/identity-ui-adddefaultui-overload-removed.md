---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637201"
---
### <a name="identity-adddefaultui-method-overload-removed"></a>Удостоверение: перегрузка метода AddDefaultUI устранена

Начиная с ASP.NET Core 3.0, перегрузка метода [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) больше не существует.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Это изменение было результатом внедрения функции статических веб-ресурсов.

#### <a name="recommended-action"></a>Рекомендованное действие

Вызывайте <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> вместо перегрузки, принимающей два аргумента. Если вы используете Bootstrap 3, добавьте следующую строку в элемент `<PropertyGroup>` в файле проекта:

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

[IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
