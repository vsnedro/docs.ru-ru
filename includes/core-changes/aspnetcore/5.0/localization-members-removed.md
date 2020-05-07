---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728302"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a>Локализация. Удален класс ResourceManagerWithCultureStringLocalizer и элемент интерфейса WithCulture

Класс [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) и метод [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) удалены в .NET 5.0, предварительная версия 1.

Контекст см. в разделах [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) и [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324). Обсуждение этого изменения см. на странице [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Представленная версия

5.0 Предварительная версия 1

#### <a name="old-behavior"></a>Старое поведение

Класс `ResourceManagerWithCultureStringLocalizer` и метод `ResourceManagerStringLocalizer.WithCulture` являются [устаревшими в .NET Core 3.0, предварительная версия 3, и более поздних версиях](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).

#### <a name="new-behavior"></a>Новое поведение

Класс `ResourceManagerWithCultureStringLocalizer` и метод `ResourceManagerStringLocalizer.WithCulture` были удалены в .NET 5.0, предварительная версия 1. Сведения о внесенных изменениях см. в запросе на вытягивание [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).

#### <a name="reason-for-change"></a>Причина изменения

Класс [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) и метод [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) часто создают путаницу для пользователей локализации. Особенно это проявляется при создании пользовательской реализации <xref:Microsoft.Extensions.Localization.IStringLocalizer>. Этот класс и метод создают ощущение, что экземпляр `IStringLocalizer` должен существовать для каждого языка и ресурса. На самом деле экземпляры различаются только для ресурсов. Во время выполнения свойство <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> определяет используемый язык.

#### <a name="recommended-action"></a>Рекомендованное действие

Прекратите использовать класс `ResourceManagerWithCultureStringLocalizer` и метод `ResourceManagerStringLocalizer.WithCulture`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
