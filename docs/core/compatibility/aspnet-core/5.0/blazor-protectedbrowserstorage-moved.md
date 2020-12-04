---
title: 'Критическое изменение. Blazor: Функция ProtectedBrowserStorage перемещена на общую платформу'
description: Сведения о критическом изменении в ASP.NET Core 5.0 — Blazor. Функция ProtectedBrowserStorage перемещена на общую платформу
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759730"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: Функция ProtectedBrowserStorage перемещена на общую платформу

В ASP.NET Core 5.0 RC2 функция `ProtectedBrowserStorage` перемещена в общую платформу ASP.NET Core.

## <a name="version-introduced"></a>Представленная версия

5.0 RC2

## <a name="old-behavior"></a>Старое поведение

В ASP.NET Core 5.0 предварительной версии 8 эта функция доступна в составе пакета [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions), но ее можно использовать только в Blazor WebAssembly.

В ASP.NET Core 5.0 RC1 эта функция доступна как часть пакета [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage), который ссылается на общую платформу `Microsoft.AspNetCore.App`.

## <a name="new-behavior"></a>Новое поведение

В ASP.NET Core 5.0 RC2 ссылка на пакет NuGet больше не требуется для обращения к этой функции и ее использования.

## <a name="reason-for-change"></a>Причина изменения

Переход на общую платформу больше соответствует ожиданиям клиентов.

## <a name="recommended-action"></a>Рекомендованное действие

При обновлении с ASP.NET Core 5.0 RC1 выполните следующие действия:

1. удалите ссылку на пакет `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` из проекта;
1. Замените `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` на `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. удалите вызов `AddProtectedBrowserStorage` из класса `Startup`.

При обновлении с ASP.NET Core 5.0 предварительной версии 8 выполните следующие действия:

1. удалите ссылку на пакет `Microsoft.AspNetCore.Components.Web.Extensions` из проекта;
1. Замените `using Microsoft.AspNetCore.Components.Web.Extensions;` на `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. удалите вызов `AddProtectedBrowserStorage` из класса `Startup`.

## <a name="affected-apis"></a>Затронутые API

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
