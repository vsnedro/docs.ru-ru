---
title: Пользовательские шаблоны для команды dotnet new
description: Сведения о пользовательских шаблонах для проектов или файлов .NET любых типов.
author: adegeo
ms.date: 05/20/2020
ms.openlocfilehash: 62d98adab0122936957301ee737c366541b0cfe6
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471554"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="0bd20-103">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="0bd20-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="0bd20-104">В состав [пакета SDK для .NET Core](https://dotnet.microsoft.com/download) входит множество шаблонов, которые уже установлены и готовы к использованию.</span><span class="sxs-lookup"><span data-stu-id="0bd20-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="0bd20-105">[Команда `dotnet new`](dotnet-new.md) позволяет не только использовать шаблоны, но и устанавливать и удалять их.</span><span class="sxs-lookup"><span data-stu-id="0bd20-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="0bd20-106">Начиная с версии .NET Core 2.0, можно создавать собственные шаблоны для проектов любого типа, например приложений, служб, средств или библиотек классов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="0bd20-107">Можно также создать шаблон, формирующий один или несколько отдельных файлов, например файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0bd20-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="0bd20-108">Устанавливать пользовательские шаблоны из пакета NuGet можно в любом веб-канале NuGet, указывая прямую ссылку на файл *NUPKG* для NuGet или каталог в файловой системе, который содержит нужный шаблон.</span><span class="sxs-lookup"><span data-stu-id="0bd20-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="0bd20-109">Модуль шаблонов предоставляет возможности, которые позволяют заменять значения, включать и исключать файлы, а также выполнять пользовательские операции обработки при использовании шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="0bd20-110">Модуль шаблонов имеет открытый код. Репозиторий кода в Интернете — [dotnet/templating](https://github.com/dotnet/templating/) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="0bd20-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="0bd20-111">Дополнительные шаблоны, в том числе шаблоны от сторонних разработчиков, можно найти на странице [Доступные шаблоны для dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="0bd20-111">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="0bd20-112">Дополнительные сведения о создании и использовании пользовательских шаблонов см. в записи блога [Создание собственных шаблонов для команды dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) и на [вики-сайте, посвященном репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="0bd20-112">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

> [!NOTE]
> <span data-ttu-id="0bd20-113">Примеры шаблонов доступны в репозитории [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) GitHub.</span><span class="sxs-lookup"><span data-stu-id="0bd20-113">Template examples are available at the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) GitHub repository.</span></span> <span data-ttu-id="0bd20-114">Но хотя эти примеры являются хорошим ресурсом для изучения работы шаблонов, репозиторий заархивирован и больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0bd20-114">However, while these examples are good resource for learning how the templates work, the repository is archived and no longer maintained.</span></span> <span data-ttu-id="0bd20-115">Примеры могут устареть и больше не работать.</span><span class="sxs-lookup"><span data-stu-id="0bd20-115">The examples may be out of date and no longer working.</span></span>

<span data-ttu-id="0bd20-116">Пошаговое руководство по созданию шаблона см. в учебнике [Создание пользовательского шаблона для команды dotnet new](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="0bd20-116">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="0bd20-117">Шаблоны .NET по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0bd20-117">.NET default templates</span></span>

<span data-ttu-id="0bd20-118">При установке [пакета SDK для .NET Core](https://dotnet.microsoft.com/download) вы получаете более десяти встроенных шаблонов для создания проектов и файлов, включая консольные приложения, библиотеки классов, проекты модульных тестов, приложения ASP.NET Core (в том числе проекты [Angular](https://angular.io/) и [React](https://reactjs.org/)) и файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0bd20-118">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://reactjs.org/) projects), and configuration files.</span></span> <span data-ttu-id="0bd20-119">Чтобы получить список встроенных шаблонов, выполните команду `dotnet new` с параметром `-l|--list`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-119">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="0bd20-120">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="0bd20-120">Configuration</span></span>

<span data-ttu-id="0bd20-121">Шаблон состоит из следующих частей:</span><span class="sxs-lookup"><span data-stu-id="0bd20-121">A template is composed of the following parts:</span></span>

- <span data-ttu-id="0bd20-122">исходные файлы и папки;</span><span class="sxs-lookup"><span data-stu-id="0bd20-122">Source files and folders.</span></span>
- <span data-ttu-id="0bd20-123">файл конфигурации ( *template.json* ).</span><span class="sxs-lookup"><span data-stu-id="0bd20-123">A configuration file ( *template.json* ).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="0bd20-124">Исходные файлы и папки</span><span class="sxs-lookup"><span data-stu-id="0bd20-124">Source files and folders</span></span>

<span data-ttu-id="0bd20-125">К исходным файлам и папкам относятся все файлы и папки, которые должен использовать модуль шаблонов при выполнении команды `dotnet new <TEMPLATE>`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-125">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="0bd20-126">Модуль шаблонов предполагает использование *запускаемых проектов* в качестве исходного кода для создания проектов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-126">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="0bd20-127">Это дает ряд преимуществ.</span><span class="sxs-lookup"><span data-stu-id="0bd20-127">This has several benefits:</span></span>

- <span data-ttu-id="0bd20-128">Модуль шаблонов не требует внедрения специальных токенов в исходный код проекта.</span><span class="sxs-lookup"><span data-stu-id="0bd20-128">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="0bd20-129">Файлы кода не являются особыми файлами и не требуют каких-либо изменений для работы с модулем шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-129">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="0bd20-130">Поэтому для работы с содержимым шаблонов можно использовать те же средства, которые вы обычно используете при работе с проектами.</span><span class="sxs-lookup"><span data-stu-id="0bd20-130">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="0bd20-131">Сборка, выполнение и отладка проектов шаблонов осуществляется так же, как и в случае с любыми другими проектами.</span><span class="sxs-lookup"><span data-stu-id="0bd20-131">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="0bd20-132">Вы можете быстро создать шаблон на основе существующего проекта, просто добавив в проект файл конфигурации *./.template.config/template.json* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-132">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="0bd20-133">Файлы и папки, которые могут храниться в шаблоне, не ограничены формальными типами проектов .NET.</span><span class="sxs-lookup"><span data-stu-id="0bd20-133">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="0bd20-134">Исходные файлы и папки могут включать в себя любое содержимое, которое требуется создавать при использовании шаблона, даже если модуль шаблонов создает только один файл в качестве выходного.</span><span class="sxs-lookup"><span data-stu-id="0bd20-134">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="0bd20-135">Создаваемые шаблоном файлы можно изменять с помощью логики и параметров, которые предоставляются в файле конфигурации *template.json* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-135">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="0bd20-136">Пользователь может переопределять эти параметры, передавая их в команду `dotnet new <TEMPLATE>`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-136">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="0bd20-137">Типичный пример пользовательской логики — определение имени класса или переменной в файле кода, который развернут с помощью шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-137">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="0bd20-138">template.json</span><span class="sxs-lookup"><span data-stu-id="0bd20-138">template.json</span></span>

<span data-ttu-id="0bd20-139">Файл *template.json* размещается в папке *.template.config* в корневом каталоге шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-139">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="0bd20-140">Он предоставляет сведения о конфигурации модулю шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-140">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="0bd20-141">В приведенной ниже таблице приведены элементы конфигурации, которые необходимы и достаточны для создания работающего шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-141">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="0bd20-142">Член</span><span class="sxs-lookup"><span data-stu-id="0bd20-142">Member</span></span>            | <span data-ttu-id="0bd20-143">Type</span><span class="sxs-lookup"><span data-stu-id="0bd20-143">Type</span></span>          | <span data-ttu-id="0bd20-144">Описание</span><span class="sxs-lookup"><span data-stu-id="0bd20-144">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="0bd20-145">URI</span><span class="sxs-lookup"><span data-stu-id="0bd20-145">URI</span></span>           | <span data-ttu-id="0bd20-146">Схема JSON для файла *template.json* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-146">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="0bd20-147">Редакторы, поддерживающие схемы JSON, обеспечивают возможности редактирования JSON при указании схемы.</span><span class="sxs-lookup"><span data-stu-id="0bd20-147">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="0bd20-148">Например, в [Visual Studio Code](https://code.visualstudio.com/) требуется, чтобы этот элемент включал поддержку IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0bd20-148">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="0bd20-149">Используйте значение `http://json.schemastore.org/template`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-149">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="0bd20-150">string</span><span class="sxs-lookup"><span data-stu-id="0bd20-150">string</span></span>        | <span data-ttu-id="0bd20-151">Автор шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-151">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="0bd20-152">array(string)</span><span class="sxs-lookup"><span data-stu-id="0bd20-152">array(string)</span></span> | <span data-ttu-id="0bd20-153">Ноль или более характеристик шаблона, по которым пользователь может найти его.</span><span class="sxs-lookup"><span data-stu-id="0bd20-153">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="0bd20-154">Если шаблон присутствует в списке шаблонов, созданных с помощью команды `dotnet new -l|--list`, классификации также приводятся в столбце *Теги* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-154">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="0bd20-155">string</span><span class="sxs-lookup"><span data-stu-id="0bd20-155">string</span></span>        | <span data-ttu-id="0bd20-156">Уникальное имя шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-156">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="0bd20-157">string</span><span class="sxs-lookup"><span data-stu-id="0bd20-157">string</span></span>        | <span data-ttu-id="0bd20-158">Имя шаблона, которое видят пользователи.</span><span class="sxs-lookup"><span data-stu-id="0bd20-158">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="0bd20-159">string</span><span class="sxs-lookup"><span data-stu-id="0bd20-159">string</span></span>        | <span data-ttu-id="0bd20-160">Сокращенное имя по умолчанию для выбора шаблона, которое используется во всех средах, где имя шаблона указывается пользователем, а не выбирается в графическом пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="0bd20-160">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="0bd20-161">Например, короткое имя полезно при использовании шаблонов из командной строки с помощью команд CLI.</span><span class="sxs-lookup"><span data-stu-id="0bd20-161">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |
| `sourceName`       | <span data-ttu-id="0bd20-162">строка</span><span class="sxs-lookup"><span data-stu-id="0bd20-162">string</span></span>        | <span data-ttu-id="0bd20-163">Имя в исходном дереве, заменяемое именем, которое указывает пользователь.</span><span class="sxs-lookup"><span data-stu-id="0bd20-163">The name in the source tree to replace with the name the user specifies.</span></span> <span data-ttu-id="0bd20-164">Обработчик шаблонов будет искать любое вхождение `sourceName`, упомянутого в файле конфигурации, и заменять его именами и содержимым файлов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-164">The template engine will look for any occurrence of the `sourceName` mentioned in the config file and replace it in file names and file contents.</span></span> <span data-ttu-id="0bd20-165">Значение, которое нужно изменить, может быть задано с помощью параметров `-n` или `--name` при выполнении шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-165">The value to be replaced with can be given using the `-n` or `--name` options while running a template.</span></span> <span data-ttu-id="0bd20-166">Если имя не указано, используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="0bd20-166">If no name is specified, the current directory is used.</span></span>|
| `preferNameDirectory`       | <span data-ttu-id="0bd20-167">Логическое</span><span class="sxs-lookup"><span data-stu-id="0bd20-167">boolean</span></span>        | <span data-ttu-id="0bd20-168">Указывает, следует ли создать каталог для шаблона, если указано имя, но выходной каталог не задан (вместо создания содержимого непосредственно в текущем каталоге).</span><span class="sxs-lookup"><span data-stu-id="0bd20-168">Indicates whether to create a directory for the template if name is specified but an output directory is not set (instead of creating the content directly in the current directory).</span></span> <span data-ttu-id="0bd20-169">Значением по умолчанию является false.</span><span class="sxs-lookup"><span data-stu-id="0bd20-169">The default value is false.</span></span>|

<span data-ttu-id="0bd20-170">Полная схема файла *template.json* находится в [хранилище схем JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="0bd20-170">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="0bd20-171">Дополнительные сведения о файле *template.json* см. на [вики-сайте о шаблонах dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="0bd20-171">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="0bd20-172">Пример</span><span class="sxs-lookup"><span data-stu-id="0bd20-172">Example</span></span>

<span data-ttu-id="0bd20-173">Например, следующая папка шаблонов включает два файла содержимого: *console.cs* и *readme.txt* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-173">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt* .</span></span> <span data-ttu-id="0bd20-174">Обратите внимание, что существует обязательная папка с именем *. template.config* и файлом *template.json* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-174">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="0bd20-175">Файл *template.json* выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="0bd20-175">The *template.json* file looks like the following:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

<span data-ttu-id="0bd20-176">Папка *mytemplate* представляет собой устанавливаемый пакет шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-176">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="0bd20-177">После установки этого пакета вы сможете использовать `shortName` с помощью команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-177">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="0bd20-178">Например, `dotnet new adatumconsole` будет выводить файлы `console.cs` и `readme.txt` в текущую папку.</span><span class="sxs-lookup"><span data-stu-id="0bd20-178">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="0bd20-179">Упаковка шаблона в пакет NuGet (файл NUPKG)</span><span class="sxs-lookup"><span data-stu-id="0bd20-179">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="0bd20-180">Пользовательский шаблон упаковывается с помощью команды [dotnet pack](dotnet-pack.md) и файла *.csproj* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-180">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="0bd20-181">Вместо этого можно применить [NuGet](/nuget/tools/nuget-exe-cli-reference) с помощью команды [nuget pack](/nuget/tools/cli-ref-pack) и файла *.nuspec* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-181">Alternatively, [NuGet](/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="0bd20-182">Но для работы NuGet требуется платформа .NET Framework в ОС Windows или [Mono](https://www.mono-project.com/) в ОС Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="0bd20-182">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and macOS.</span></span>

<span data-ttu-id="0bd20-183">Этот файл *.csproj* несколько отличается от традиционных файлов *.csproj* в проектах кода.</span><span class="sxs-lookup"><span data-stu-id="0bd20-183">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="0bd20-184">Обратите внимание на следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0bd20-184">Note the following settings:</span></span>

01. <span data-ttu-id="0bd20-185">Добавляется параметр `<PackageType>` со значением `Template`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-185">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="0bd20-186">Добавляется параметр `<PackageVersion>` со значением допустимой [версии NuGet](/nuget/reference/package-versioning).</span><span class="sxs-lookup"><span data-stu-id="0bd20-186">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="0bd20-187">Добавляется параметр `<PackageId>` со значением уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0bd20-187">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="0bd20-188">Этот идентификатор используется для удаления пакета шаблона, а также в веб-каналах NuGet для регистрации пакета шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-188">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="0bd20-189">Нужно задать параметры для универсальных метаданных: `<Title>`, `<Authors>`, `<Description>` и `<PackageTags>`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-189">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="0bd20-190">Нужно задать параметр `<TargetFramework>`, даже если не используется созданный процессом шаблона двоичный файл.</span><span class="sxs-lookup"><span data-stu-id="0bd20-190">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="0bd20-191">В приведенном ниже примере он имеет значение `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-191">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="0bd20-192">Пакет шаблонов в формате пакета NuGet *.nupkg* ожидает, что все шаблоны будут сохранены в папке *content* внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="0bd20-192">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="0bd20-193">Есть еще несколько параметров, которые нужно добавить в файл *.csproj* , чтобы созданный файл *.nupkg* можно было установить как пакет шаблонов:</span><span class="sxs-lookup"><span data-stu-id="0bd20-193">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="0bd20-194">Параметр `<IncludeContentInPack>` получает значение `true`, чтобы включить все файлы проекта, отмеченные в пакете NuGet как содержимое ( **content** ).</span><span class="sxs-lookup"><span data-stu-id="0bd20-194">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="0bd20-195">Параметр `<IncludeBuildOutput>` получает значение `false`, чтобы исключить все бинарные файлы, созданные компилятором из пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="0bd20-195">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="0bd20-196">Параметр `<ContentTargetFolders>` получает значение `content`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-196">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="0bd20-197">Это гарантирует, что указанные в качестве содержимого ( **content** ) файлы будут сохранены в папку *content* в пакете NuGet.</span><span class="sxs-lookup"><span data-stu-id="0bd20-197">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="0bd20-198">Эта папка в пакете NuGet анализируется системой шаблонов dotnet.</span><span class="sxs-lookup"><span data-stu-id="0bd20-198">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="0bd20-199">Вы можете легко исключить все файлы кода из компиляции с проектом шаблона, указав элемент `<Compile Remove="**\*" />` в файле проекта, внутри элемента `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-199">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="0bd20-200">Чтобы структурировать пакет шаблонов, можно поместить все шаблоны в отдельные папки, а сами эти папки шаблонов — в папку *templates* в том же каталоге, где расположен файл *.csproj* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-200">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="0bd20-201">Это позволит вам использовать один элемент проекта для включения всех файлов и папок из папки *templates* в качестве содержимого ( **content** ).</span><span class="sxs-lookup"><span data-stu-id="0bd20-201">This way, you can use a single project item to include all files and folders in the *templates* as **content** .</span></span> <span data-ttu-id="0bd20-202">Внутри элемента `<ItemGroup>` создайте элемент `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-202">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="0bd20-203">Вот пример файла *.csproj* , созданного с соблюдением всех указанных выше рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="0bd20-203">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="0bd20-204">Он упаковывает дочернюю папку *templates* в папку пакета *content* и исключает из компиляции все файлы кода.</span><span class="sxs-lookup"><span data-stu-id="0bd20-204">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="0bd20-205">В приведенном ниже примере показана структура файлов и папок, полученная при создании пакета шаблонов с помощью файла *.csproj* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-205">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="0bd20-206">Файл *MyDotnetTemplates.csproj* и папка *templates* размещаются в корневом каталоге с именем *project_folder* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-206">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder* .</span></span> <span data-ttu-id="0bd20-207">Папка *templates* содержит два шаблона с именами *mytemplate1* и *mytemplate2* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-207">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2* .</span></span> <span data-ttu-id="0bd20-208">Каждый шаблон включает файлы содержимого и папку *.template.config* с файлом конфигурации *template.json* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-208">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a><span data-ttu-id="0bd20-209">Установка шаблона</span><span class="sxs-lookup"><span data-stu-id="0bd20-209">Installing a template</span></span>

<span data-ttu-id="0bd20-210">Чтобы установить пакет, выполните команду [dotnet new -i|--install](dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="0bd20-210">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="0bd20-211">Установка шаблона из пакета NuGet, хранящегося на сайте nuget.org</span><span class="sxs-lookup"><span data-stu-id="0bd20-211">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="0bd20-212">Для установки пакета шаблонов используйте идентификатор пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="0bd20-212">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="0bd20-213">Установка шаблона из локального файла NUPKG</span><span class="sxs-lookup"><span data-stu-id="0bd20-213">To install a template from a local nupkg file</span></span>

<span data-ttu-id="0bd20-214">Укажите путь к файлу *.nupkg* пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="0bd20-214">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="0bd20-215">Установка шаблона из каталога в файловой системе</span><span class="sxs-lookup"><span data-stu-id="0bd20-215">To install a template from a file system directory</span></span>

<span data-ttu-id="0bd20-216">Шаблоны можно установить из папки шаблонов, например из папки *mytemplate1* в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="0bd20-216">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="0bd20-217">Укажите путь к папке *.template.config* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-217">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="0bd20-218">Не обязательно указывать абсолютный путь к каталогу шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-218">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="0bd20-219">Но для удаления шаблона, который был установлен из папки, требуется абсолютный путь.</span><span class="sxs-lookup"><span data-stu-id="0bd20-219">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="0bd20-220">Получение списка установленных шаблонов</span><span class="sxs-lookup"><span data-stu-id="0bd20-220">Get a list of installed templates</span></span>

<span data-ttu-id="0bd20-221">Команда удаления (uninstall) без дополнительных параметров возвращает полный список установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-221">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="0bd20-222">Эта команда возвращает примерно следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="0bd20-222">That command returns something similar to the following output:</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

<span data-ttu-id="0bd20-223">На первом уровне элементов под `Currently installed items:` расположены идентификаторы, используемые для удаления шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bd20-223">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="0bd20-224">В представленном выше примере в список входят `Microsoft.DotNet.Common.ItemTemplates` и `Microsoft.DotNet.Common.ProjectTemplates.3.0`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-224">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="0bd20-225">Если шаблон был установлен через путь файловой системы, этот идентификатор совпадает с путем к папке *.template.config* .</span><span class="sxs-lookup"><span data-stu-id="0bd20-225">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="0bd20-226">Удаление шаблона</span><span class="sxs-lookup"><span data-stu-id="0bd20-226">Uninstalling a template</span></span>

<span data-ttu-id="0bd20-227">Чтобы установить пакет, выполните команду [dotnet new -u|--uninstall](dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="0bd20-227">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="0bd20-228">Если пакет был установлен веб-каналом NuGet или напрямую из файла *.nupkg* , вам нужно предоставить идентификатор для него.</span><span class="sxs-lookup"><span data-stu-id="0bd20-228">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="0bd20-229">Если пакет был установлен указанием пути к папке *.template.config* , используйте тот же **абсолютный** путь для удаления пакета.</span><span class="sxs-lookup"><span data-stu-id="0bd20-229">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="0bd20-230">Абсолютный путь к шаблону можно найти в выходных данных команды `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="0bd20-230">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="0bd20-231">Дополнительные сведения см. выше в разделе [Получение списка установленных шаблонов](#get-a-list-of-installed-templates).</span><span class="sxs-lookup"><span data-stu-id="0bd20-231">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="0bd20-232">Создание проекта с помощью пользовательского шаблона</span><span class="sxs-lookup"><span data-stu-id="0bd20-232">Create a project using a custom template</span></span>

<span data-ttu-id="0bd20-233">После установки шаблона для его использования выполните команду `dotnet new <TEMPLATE>` так же, как и в случае с любым другим предустановленным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="0bd20-233">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="0bd20-234">Кроме того, можно указать [параметры](dotnet-new.md#options) для команды `dotnet new`, в том числе относящиеся к шаблону параметры, заданные в настройках шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bd20-234">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="0bd20-235">Укажите короткое имя шаблона непосредственно в команде.</span><span class="sxs-lookup"><span data-stu-id="0bd20-235">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="0bd20-236">См. также</span><span class="sxs-lookup"><span data-stu-id="0bd20-236">See also</span></span>

- [<span data-ttu-id="0bd20-237">Создание пользовательского шаблона для команды dotnet new (учебник)</span><span class="sxs-lookup"><span data-stu-id="0bd20-237">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="0bd20-238">Вики-сайт, посвященный репозиторию dotnet/templating в GitHub</span><span class="sxs-lookup"><span data-stu-id="0bd20-238">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="0bd20-239">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="0bd20-239">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="0bd20-240">Создание собственных шаблонов для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="0bd20-240">How to create your own templates for dotnet new</span></span>](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- [<span data-ttu-id="0bd20-241">Схема *template.json* в хранилище схем JSON</span><span class="sxs-lookup"><span data-stu-id="0bd20-241">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
