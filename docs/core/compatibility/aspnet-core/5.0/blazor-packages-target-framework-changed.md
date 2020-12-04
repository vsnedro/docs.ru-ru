---
title: 'Критическое изменение. Blazor: Изменена целевая платформа для пакетов NuGet'
description: Сведения о критическом изменении в ASP.NET Core 5.0 — Blazor. Изменена целевая платформа для пакетов NuGet
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 5515edc66ff9786f0d8f7e24e5fc28c71502567b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759733"
---
# <a name="blazor-target-framework-of-nuget-packages-changed"></a>Blazor: Изменена целевая платформа для пакетов NuGet

Ранее проекты Blazor 3.2 WebAssembly компилировались для целевой платформы .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`). В ASP.NET Core 5.0 целевой платформой для проектов Blazor Server и Blazor WebAssembly является .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`). В соответствии с изменением целевой платформы следующие пакеты Blazor также больше не предназначены для платформы .NET Standard 2.1:

* [Microsoft.AspNetCore.Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components);
* [Microsoft.AspNetCore.Components.Authorization](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [Microsoft.AspNetCore.Components.Forms](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [Microsoft.AspNetCore.Components.Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web).
* [Microsoft.AspNetCore.Components.WebAssembly](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [Microsoft.AspNetCore.Components.WebAssembly.Authentication](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [Microsoft.JSInterop](https://www.nuget.org/packages/Microsoft.JSInterop)
* [Microsoft.JSInterop.WebAssembly](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [Microsoft.Authentication.WebAssembly.Msal](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).

## <a name="version-introduced"></a>Представленная версия

5.0 (предварительная версия 7)

## <a name="old-behavior"></a>Старое поведение

В Blazor 3.1 и 3.2 пакеты были предназначены для платформ .NET Standard 2.1 и .NET Core 3.1.

## <a name="new-behavior"></a>Новое поведение

В ASP.NET Core 5.0 пакеты предназначены для платформы .NET 5.0.

## <a name="reason-for-change"></a>Причина изменения

Эти изменения были внесены в соответствии с требованиями к целевой платформе .NET.

## <a name="recommended-action"></a>Рекомендованное действие

Для проектов Blazor 3.2 WebAssembly следует задавать .NET 5.0 в качестве целевой платформы в рамках обновления ссылок на пакеты до версии 5.x.x. Библиотеки, ссылающиеся на эти пакеты, могут быть предназначены для .NET 5.0 или сразу для нескольких платформ в зависимости от требований.

## <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
