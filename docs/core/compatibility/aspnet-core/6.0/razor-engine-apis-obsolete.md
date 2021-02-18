---
title: Критическое изменение. Razor. Интерфейсы API RazorEngine помечены как устаревшие
description: Сведения о критическом изменении в ASP.NET Core 6.0 — Razor. Интерфейсы API RazorEngine помечены как устаревшие
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: 173ff0ee5c062f050c967c6edc7bed333d1a2031
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488227"
---
# <a name="razor-razorengine-apis-marked-obsolete"></a>Razor. Интерфейсы API RazorEngine помечены как устаревшие

Типы, связанные с типом <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> в Blazor, помечены как устаревшие.

## <a name="version-introduced"></a>Представленная версия

6.0, предварительная версия 1

## <a name="old-behavior"></a>Старое поведение

Интерфейсы API `RazorEngine` не являются устаревшими.

## <a name="new-behavior"></a>Новое поведение

API `RazorEngine` являются устаревшими.

## <a name="reason-for-change"></a>Причина изменения

Вместо типа `RazorEngine` теперь следует использовать тип <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.

## <a name="recommended-action"></a>Рекомендованное действие

Перенос исходного кода из типа `RazorEngine` в тип `RazorProjectEngine`.

## <a name="affected-apis"></a>Затронутые API

- [Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.injectdirective.register?view=aspnetcore-3.1&preserve-view=true)
- [Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.functionsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.inheritsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.sectiondirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder](/dotnet/api/microsoft.aspnetcore.razor.language.irazorenginebuilder?view=aspnetcore-3.0&preserve-view=true)

<!--

## Category

ASP.NET Core

## Affected APIs

- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register`
- `T:Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder`

-->
