---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391186"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>Статические файлы. Тип содержимого CSV изменен на соответствующий стандартам

В ASP.NET Core 5.0 значение заголовка ответа `Content-Type` по умолчанию, используемое [ПО промежуточного слоя для статических файлов](/aspnet/core/fundamentals/static-files) для *CSV*-файлов, изменилось на соответствующее стандартам значение `text/csv`.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).

#### <a name="version-introduced"></a>Представленная версия

5.0 Предварительная версия 1

#### <a name="old-behavior"></a>Старое поведение

Использовалось значение `application/octet-stream` заголовка `Content-Type`.

#### <a name="new-behavior"></a>Новое поведение

Используется значение `text/csv` заголовка `Content-Type`.

#### <a name="reason-for-change"></a>Причина изменения

Соответствие стандарту [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1).

#### <a name="recommended-action"></a>Рекомендованное действие

Если это изменение влияет на приложение, можно настроить сопоставление расширения файла с типом MIME. Чтобы вернуться к типу MIME `application/octet-stream`, измените вызов метода <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> в `Startup.Configure`. Пример:

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

Дополнительные сведения о настройке сопоставления см. в разделе [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
