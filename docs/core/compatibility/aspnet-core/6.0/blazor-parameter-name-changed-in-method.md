---
title: 'Критическое изменение. Blazor: изменено имя параметра в методе RequestImageFileAsync'
description: Сведения о критическом изменении в ASP.NET Core 6.0 — Blazor. изменено имя параметра в методе RequestImageFileAsync
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: bfaaa6bfe94c32fbc1a5b5b70db863d105d389b5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488264"
---
# <a name="blazor-parameter-name-changed-in-requestimagefileasync-method"></a>Blazor: изменено имя параметра в методе RequestImageFileAsync

Параметр `maxWith` метода `RequestImageFileAsync` был переименован из `maxWith` в `maxWidth`.

## <a name="version-introduced"></a>Представленная версия

6.0, предварительная версия 1

## <a name="old-behavior"></a>Старое поведение

Имя параметра пишется как `maxWith`.

## <a name="new-behavior"></a>Новое поведение

Имя параметра пишется как `maxWidth`.

## <a name="reason-for-change"></a>Причина изменения

Исходное имя параметра было типографической ошибкой.

## <a name="recommended-action"></a>Рекомендованное действие

Если вы используете именованные параметры в API `RequestImageFile`, измените имя параметра `maxWith` на `maxWidth`. В противном случае изменение не требуется.

## <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync`

-->
