---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032846"
---
### <a name="razor-razortemplateengine-api-removed"></a>Razor. Удален API RazorTemplateEngine

API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) был удален и заменен на <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.

Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Для синтаксического анализа и создания кода для файлов Razor можно создать и использовать обработчик шаблонов.

#### <a name="new-behavior"></a>Новое поведение

Можно создать `RazorProjectEngine` и предоставить сведения того же типа, что и `RazorTemplateEngine` для анализа и создания кода для файлов Razor. `RazorProjectEngine` также предоставляет дополнительные уровни конфигурации.

#### <a name="reason-for-change"></a>Причина изменения

`RazorTemplateEngine` был слишком тесно связан с существующими реализациями. Эта тесная связь приводит к дополнительным вопросам при попытке правильной настройки конвейера анализа и формирования Razor.

#### <a name="recommended-action"></a>Рекомендованное действие

Используйте `RazorProjectEngine` вместо `RazorTemplateEngine`. Рассмотрим следующие примеры.

##### <a name="create-and-configure-the-razorprojectengine"></a>Создание и настройка RazorProjectEngine

```csharp
RazorProjectEngine projectEngine =
    RazorProjectEngine.Create(RazorConfiguration.Default,
        RazorProjectFileSystem.Create(@"C:\source\repos\ConsoleApp4\ConsoleApp4"),
        builder =>
        {
            builder.ConfigureClass((document, classNode) =>
            {
                classNode.ClassName = "MyClassName";

                // Can also configure other aspects of the class here.
            });

            // More configuration can go here
        });
```

##### <a name="generate-code-for-a-razor-file"></a>Создание кода для файла Razor

```csharp
RazorProjectItem item = projectEngine.FileSystem.GetItem(
    @"C:\source\repos\ConsoleApp4\ConsoleApp4\Example.cshtml",
    FileKinds.Legacy);
RazorCodeDocument output = projectEngine.Process(item);

// Things available
RazorSyntaxTree syntaxTree = output.GetSyntaxTree();
DocumentIntermediateNode intermediateDocument =
    output.GetDocumentIntermediateNode();
RazorCSharpDocument csharpDocument = output.GetCSharpDocument();
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [RazorTemplateEngineOptions](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
