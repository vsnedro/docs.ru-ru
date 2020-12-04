---
title: Критическое изменение. Локализация. Из ПО промежуточного слоя локализации запроса удален устаревший конструктор
description: Сведения о критическом изменении в ASP.NET Core 5.0 — локализация. Из ПО промежуточного слоя локализации запроса удален устаревший конструктор
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 53dd0f25078dae140d34d6d21d66983f78b8bdb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759958"
---
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a>Локализация. Из ПО промежуточного слоя локализации запроса удален устаревший конструктор

Конструктор <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware>, в котором отсутствует параметр <xref:Microsoft.Extensions.Logging.ILoggerFactory>, был помечен [в этой фиксации](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0) как устаревший. В ASP.NET Core 5.0 устаревший конструктор был удален. Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).

## <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

## <a name="old-behavior"></a>Старое поведение

Присутствует устаревший конструктор `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)`.

## <a name="new-behavior"></a>Новое поведение

Устаревший конструктор `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` удален.

## <a name="reason-for-change"></a>Причина изменения

Это изменение гарантирует, что ПО промежуточного слоя локализации запроса будет всегда иметь доступ к средству ведения журнала.

## <a name="recommended-action"></a>Рекомендованное действие

При создании экземпляра `RequestLocalizationMiddleware` вручную передайте экземпляр `ILoggerFactory` в конструкторе. Если допустимый экземпляр `ILoggerFactory` недоступен в этом контексте, попробуйте передать конструктор ПО промежуточного слоя экземпляру <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory>.

## <a name="affected-apis"></a>Затронутые API

[RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
