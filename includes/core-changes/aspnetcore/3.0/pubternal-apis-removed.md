---
ms.openlocfilehash: b1fb9647091cecb80b9c2f04ec9b6bb156eb39ba
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84466840"
---
### <a name="pubternal-apis-removed"></a>Удалены API-интерфейсы Pubternal

Чтобы сохранить порядок в предоставляемой поверхности API платформы ASP.NET Core, большинство типов в пространствах имен `*.Internal` (которые называются API-интерфейсами :::no-loc text="\"pubternal\"":::) стали по-настоящему внутренними. Элементы в этих пространствах имен никогда не предполагалось поддерживать в качестве общедоступных API-интерфейсов. Для этих API-интерфейсов допускались критические изменения в дополнительных выпусках. Такие изменения применялись часто. Любой код, который зависит от этих API-интерфейсов, перестанет работать при обновлении до ASP.NET Core 3.0.

Подробную информацию см. на страницах [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) и [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Затронутые API-интерфейсы помечаются модификатором доступа `public` и существуют в пространствах имен `*.Internal`.

#### <a name="new-behavior"></a>Новое поведение

Затронутые API-интерфейсы помечаются модификатором доступа [internal](/dotnet/csharp/language-reference/keywords/internal) и больше не могут использоваться в коде за пределами этой сборки.

#### <a name="reason-for-change"></a>Причина изменения

Для этих API-интерфейсов :::no-loc text="\"pubternal\""::: всегда действовали следующие предупреждения:

* Они могут измениться без предварительного уведомления.
* На них не распространяются политики .NET по контролю критических изменений.

Сохранение API-интерфейсов `public` (даже в пространстве имен `*.Internal`) неоднозначно воспринималось пользователями.

#### <a name="recommended-action"></a>Рекомендованное действие

Прекратите использовать API-интерфейсы :::no-loc text="\"pubternal\"":::. Если вы хотите узнать, какие API-интерфейсы лучше использовать вместо них, откройте запрос в репозитории [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

Для примера давайте рассмотрим приведенный ниже код, который буферизует HTTP-запросы в проекте ASP.NET Core 2.2. Методы расширения `EnableRewind` относятся к пространству имен `Microsoft.AspNetCore.Http.Internal`.

```csharp
HttpContext.Request.EnableRewind();
```

В проекте ASP.NET Core 3.0 замените вызов `EnableRewind` вызовом метода расширения `EnableBuffering`. Теперь функция буферизации запросов работает так же, как раньше. Но теперь `EnableBuffering` вызывает API `internal`.

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Все API-интерфейсы в пространствах имен `Microsoft.AspNetCore.*` и `Microsoft.Extensions.*`, в имени пространства имен которых есть сегмент `Internal`. Пример:

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
