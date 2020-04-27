---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102831"
---
# <a name="dotnet-new"></a><span data-ttu-id="8e657-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8e657-103">dotnet new</span></span>

<span data-ttu-id="8e657-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8e657-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8e657-105">name</span><span class="sxs-lookup"><span data-stu-id="8e657-105">Name</span></span>

<span data-ttu-id="8e657-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8e657-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8e657-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="8e657-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8e657-108">Description</span></span>

<span data-ttu-id="8e657-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="8e657-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="8e657-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="8e657-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="8e657-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8e657-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="8e657-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="8e657-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="8e657-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="8e657-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="8e657-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="8e657-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="8e657-116">Вы можете запустить `dotnet new --list`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="8e657-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="8e657-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="8e657-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="8e657-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="8e657-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="8e657-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="8e657-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="8e657-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="8e657-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="8e657-122">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e657-122">The command contains a default list of templates.</span></span> <span data-ttu-id="8e657-123">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="8e657-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8e657-124">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8e657-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="8e657-125">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="8e657-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="8e657-126">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="8e657-127">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="8e657-127">Templates</span></span>                                    | <span data-ttu-id="8e657-128">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="8e657-128">Short name</span></span>                      | <span data-ttu-id="8e657-129">Язык</span><span class="sxs-lookup"><span data-stu-id="8e657-129">Language</span></span>     | <span data-ttu-id="8e657-130">Tags</span><span class="sxs-lookup"><span data-stu-id="8e657-130">Tags</span></span>                                  | <span data-ttu-id="8e657-131">Введенный</span><span class="sxs-lookup"><span data-stu-id="8e657-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="8e657-132">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="8e657-132">Console Application</span></span>                          | [<span data-ttu-id="8e657-133">Консоль</span><span class="sxs-lookup"><span data-stu-id="8e657-133">console</span></span>](#console)             | <span data-ttu-id="8e657-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e657-134">[C#], F#, VB</span></span> | <span data-ttu-id="8e657-135">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="8e657-135">Common/Console</span></span>                        | <span data-ttu-id="8e657-136">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-136">1.0</span></span>        |
| <span data-ttu-id="8e657-137">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="8e657-137">Class library</span></span>                                | [<span data-ttu-id="8e657-138">classlib</span><span class="sxs-lookup"><span data-stu-id="8e657-138">classlib</span></span>](#classlib)           | <span data-ttu-id="8e657-139">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e657-139">[C#], F#, VB</span></span> | <span data-ttu-id="8e657-140">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="8e657-140">Common/Library</span></span>                        | <span data-ttu-id="8e657-141">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-141">1.0</span></span>        |
| <span data-ttu-id="8e657-142">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-142">WPF Application</span></span>                              | [<span data-ttu-id="8e657-143">wpf</span><span class="sxs-lookup"><span data-stu-id="8e657-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="8e657-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-144">[C#]</span></span>         | <span data-ttu-id="8e657-145">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-145">Common/WPF</span></span>                            | <span data-ttu-id="8e657-146">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-146">3.0</span></span>        |
| <span data-ttu-id="8e657-147">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-147">WPF Class library</span></span>                            | [<span data-ttu-id="8e657-148">wpflib</span><span class="sxs-lookup"><span data-stu-id="8e657-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="8e657-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-149">[C#]</span></span>         | <span data-ttu-id="8e657-150">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-150">Common/WPF</span></span>                            | <span data-ttu-id="8e657-151">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-151">3.0</span></span>        |
| <span data-ttu-id="8e657-152">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="8e657-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="8e657-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="8e657-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-154">[C#]</span></span>         | <span data-ttu-id="8e657-155">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-155">Common/WPF</span></span>                            | <span data-ttu-id="8e657-156">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-156">3.0</span></span>        |
| <span data-ttu-id="8e657-157">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="8e657-158">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="8e657-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="8e657-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-159">[C#]</span></span>         | <span data-ttu-id="8e657-160">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="8e657-160">Common/WPF</span></span>                            | <span data-ttu-id="8e657-161">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-161">3.0</span></span>        |
| <span data-ttu-id="8e657-162">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="8e657-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="8e657-163">winforms</span><span class="sxs-lookup"><span data-stu-id="8e657-163">winforms</span></span>](#winforms)           | <span data-ttu-id="8e657-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-164">[C#]</span></span>         | <span data-ttu-id="8e657-165">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="8e657-165">Common/WinForms</span></span>                       | <span data-ttu-id="8e657-166">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-166">3.0</span></span>        |
| <span data-ttu-id="8e657-167">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="8e657-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="8e657-168">winformslib</span><span class="sxs-lookup"><span data-stu-id="8e657-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="8e657-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-169">[C#]</span></span>         | <span data-ttu-id="8e657-170">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="8e657-170">Common/WinForms</span></span>                       | <span data-ttu-id="8e657-171">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-171">3.0</span></span>        |
| <span data-ttu-id="8e657-172">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="8e657-172">Worker Service</span></span>                               | [<span data-ttu-id="8e657-173">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="8e657-173">worker</span></span>](#web-others)           | <span data-ttu-id="8e657-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-174">[C#]</span></span>         | <span data-ttu-id="8e657-175">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="8e657-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="8e657-176">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-176">3.0</span></span>        |
| <span data-ttu-id="8e657-177">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="8e657-177">Unit Test Project</span></span>                            | [<span data-ttu-id="8e657-178">mstest</span><span class="sxs-lookup"><span data-stu-id="8e657-178">mstest</span></span>](#test)                 | <span data-ttu-id="8e657-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e657-179">[C#], F#, VB</span></span> | <span data-ttu-id="8e657-180">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="8e657-180">Test/MSTest</span></span>                           | <span data-ttu-id="8e657-181">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-181">1.0</span></span>        |
| <span data-ttu-id="8e657-182">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="8e657-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="8e657-183">nunit</span><span class="sxs-lookup"><span data-stu-id="8e657-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="8e657-184">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e657-184">[C#], F#, VB</span></span> | <span data-ttu-id="8e657-185">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="8e657-185">Test/NUnit</span></span>                            | <span data-ttu-id="8e657-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="8e657-186">2.1.400</span></span>    |
| <span data-ttu-id="8e657-187">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="8e657-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="8e657-188">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e657-188">[C#], F#, VB</span></span> | <span data-ttu-id="8e657-189">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="8e657-189">Test/NUnit</span></span>                            | <span data-ttu-id="8e657-190">2.2</span><span class="sxs-lookup"><span data-stu-id="8e657-190">2.2</span></span>        |
| <span data-ttu-id="8e657-191">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="8e657-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="8e657-192">xunit</span><span class="sxs-lookup"><span data-stu-id="8e657-192">xunit</span></span>](#test)                  | <span data-ttu-id="8e657-193">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e657-193">[C#], F#, VB</span></span> | <span data-ttu-id="8e657-194">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="8e657-194">Test/xUnit</span></span>                            | <span data-ttu-id="8e657-195">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-195">1.0</span></span>        |
| <span data-ttu-id="8e657-196">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="8e657-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="8e657-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-197">[C#]</span></span>         | <span data-ttu-id="8e657-198">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e657-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="8e657-199">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-199">3.0</span></span>        |
| <span data-ttu-id="8e657-200">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="8e657-200">Razor Page</span></span>                                   | [<span data-ttu-id="8e657-201">page</span><span class="sxs-lookup"><span data-stu-id="8e657-201">page</span></span>](#page)                   | <span data-ttu-id="8e657-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-202">[C#]</span></span>         | <span data-ttu-id="8e657-203">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e657-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="8e657-204">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-204">2.0</span></span>        |
| <span data-ttu-id="8e657-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8e657-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="8e657-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="8e657-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="8e657-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-207">[C#]</span></span>         | <span data-ttu-id="8e657-208">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e657-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="8e657-209">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-209">2.0</span></span>        |
| <span data-ttu-id="8e657-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8e657-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="8e657-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-211">[C#]</span></span>         | <span data-ttu-id="8e657-212">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e657-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="8e657-213">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-213">2.0</span></span>        |
| <span data-ttu-id="8e657-214">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="8e657-214">Blazor Server App</span></span>                            | [<span data-ttu-id="8e657-215">blazorserver</span><span class="sxs-lookup"><span data-stu-id="8e657-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="8e657-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-216">[C#]</span></span>         | <span data-ttu-id="8e657-217">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="8e657-217">Web/Blazor</span></span>                            | <span data-ttu-id="8e657-218">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-218">3.0</span></span>        |
| <span data-ttu-id="8e657-219">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8e657-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="8e657-220">web</span><span class="sxs-lookup"><span data-stu-id="8e657-220">web</span></span>](#web)                     | <span data-ttu-id="8e657-221">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e657-221">[C#], F#</span></span>     | <span data-ttu-id="8e657-222">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="8e657-222">Web/Empty</span></span>                             | <span data-ttu-id="8e657-223">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-223">1.0</span></span>        |
| <span data-ttu-id="8e657-224">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="8e657-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="8e657-225">mvc</span><span class="sxs-lookup"><span data-stu-id="8e657-225">mvc</span></span>](#web-options)             | <span data-ttu-id="8e657-226">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e657-226">[C#], F#</span></span>     | <span data-ttu-id="8e657-227">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="8e657-227">Web/MVC</span></span>                               | <span data-ttu-id="8e657-228">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-228">1.0</span></span>        |
| <span data-ttu-id="8e657-229">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8e657-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="8e657-230">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="8e657-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="8e657-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-231">[C#]</span></span>         | <span data-ttu-id="8e657-232">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="8e657-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="8e657-233">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="8e657-234">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="8e657-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="8e657-235">angular</span><span class="sxs-lookup"><span data-stu-id="8e657-235">angular</span></span>](#spa)                 | <span data-ttu-id="8e657-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-236">[C#]</span></span>         | <span data-ttu-id="8e657-237">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="8e657-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8e657-238">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-238">2.0</span></span>        |
| <span data-ttu-id="8e657-239">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="8e657-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="8e657-240">react</span><span class="sxs-lookup"><span data-stu-id="8e657-240">react</span></span>](#spa)                   | <span data-ttu-id="8e657-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-241">[C#]</span></span>         | <span data-ttu-id="8e657-242">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="8e657-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8e657-243">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-243">2.0</span></span>        |
| <span data-ttu-id="8e657-244">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="8e657-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="8e657-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="8e657-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="8e657-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-246">[C#]</span></span>         | <span data-ttu-id="8e657-247">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="8e657-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8e657-248">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-248">2.0</span></span>        |
| <span data-ttu-id="8e657-249">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="8e657-249">Razor Class Library</span></span>                          | [<span data-ttu-id="8e657-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="8e657-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="8e657-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-251">[C#]</span></span>         | <span data-ttu-id="8e657-252">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="8e657-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="8e657-253">2.1</span><span class="sxs-lookup"><span data-stu-id="8e657-253">2.1</span></span>        |
| <span data-ttu-id="8e657-254">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8e657-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="8e657-255">webapi</span><span class="sxs-lookup"><span data-stu-id="8e657-255">webapi</span></span>](#webapi)               | <span data-ttu-id="8e657-256">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e657-256">[C#], F#</span></span>     | <span data-ttu-id="8e657-257">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="8e657-257">Web/WebAPI</span></span>                            | <span data-ttu-id="8e657-258">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-258">1.0</span></span>        |
| <span data-ttu-id="8e657-259">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="8e657-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="8e657-260">grpc</span><span class="sxs-lookup"><span data-stu-id="8e657-260">grpc</span></span>](#web-others)             | <span data-ttu-id="8e657-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e657-261">[C#]</span></span>         | <span data-ttu-id="8e657-262">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="8e657-262">Web/gRPC</span></span>                              | <span data-ttu-id="8e657-263">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-263">3.0</span></span>        |
| <span data-ttu-id="8e657-264">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="8e657-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="8e657-265">proto</span><span class="sxs-lookup"><span data-stu-id="8e657-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="8e657-266">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="8e657-266">Web/gRPC</span></span>                              | <span data-ttu-id="8e657-267">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-267">3.0</span></span>        |
| <span data-ttu-id="8e657-268">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="8e657-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="8e657-269">Config</span><span class="sxs-lookup"><span data-stu-id="8e657-269">Config</span></span>                                | <span data-ttu-id="8e657-270">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-270">3.0</span></span>        |
| <span data-ttu-id="8e657-271">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="8e657-271">global.json file</span></span>                             | [<span data-ttu-id="8e657-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="8e657-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="8e657-273">Config</span><span class="sxs-lookup"><span data-stu-id="8e657-273">Config</span></span>                                | <span data-ttu-id="8e657-274">2.0</span><span class="sxs-lookup"><span data-stu-id="8e657-274">2.0</span></span>        |
| <span data-ttu-id="8e657-275">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="8e657-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="8e657-276">Config</span><span class="sxs-lookup"><span data-stu-id="8e657-276">Config</span></span>                                | <span data-ttu-id="8e657-277">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-277">1.0</span></span>        |
| <span data-ttu-id="8e657-278">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="8e657-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="8e657-279">Config</span><span class="sxs-lookup"><span data-stu-id="8e657-279">Config</span></span>                                | <span data-ttu-id="8e657-280">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-280">3.0</span></span>        |
| <span data-ttu-id="8e657-281">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="8e657-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="8e657-282">Config</span><span class="sxs-lookup"><span data-stu-id="8e657-282">Config</span></span>                                | <span data-ttu-id="8e657-283">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-283">1.0</span></span>        |
| <span data-ttu-id="8e657-284">Файл решения</span><span class="sxs-lookup"><span data-stu-id="8e657-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="8e657-285">Решение</span><span class="sxs-lookup"><span data-stu-id="8e657-285">Solution</span></span>                              | <span data-ttu-id="8e657-286">1.0</span><span class="sxs-lookup"><span data-stu-id="8e657-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="8e657-287">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e657-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="8e657-288">Отображает сводку того, что произойдет, если выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="8e657-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="8e657-289">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="8e657-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="8e657-290">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="8e657-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8e657-291">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e657-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e657-292">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="8e657-292">Prints out help for the command.</span></span> <span data-ttu-id="8e657-293">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="8e657-294">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="8e657-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="8e657-295">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="8e657-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8e657-296">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="8e657-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8e657-297">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="8e657-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="8e657-298">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="8e657-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="8e657-299">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="8e657-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="8e657-300">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="8e657-301">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="8e657-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="8e657-302">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="8e657-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="8e657-303">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-303">The language of the template to create.</span></span> <span data-ttu-id="8e657-304">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="8e657-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8e657-305">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="8e657-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e657-306">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="8e657-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8e657-307">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8e657-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="8e657-308">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="8e657-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="8e657-309">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8e657-309">The name for the created output.</span></span> <span data-ttu-id="8e657-310">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="8e657-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="8e657-311">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="8e657-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="8e657-312">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="8e657-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8e657-313">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8e657-313">Location to place the generated output.</span></span> <span data-ttu-id="8e657-314">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8e657-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="8e657-315">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="8e657-315">Filters templates based on available types.</span></span> <span data-ttu-id="8e657-316">Предопределенные значения: `project`, `item` или `other`.</span><span class="sxs-lookup"><span data-stu-id="8e657-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="8e657-317">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="8e657-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8e657-318">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="8e657-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="8e657-319">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="8e657-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="8e657-320">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="8e657-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e657-321">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="8e657-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8e657-322">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="8e657-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="8e657-323">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="8e657-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="8e657-324">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="8e657-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="8e657-325">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="8e657-326">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="8e657-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="8e657-327">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="8e657-328">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="8e657-328">Template options</span></span>

<span data-ttu-id="8e657-329">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="8e657-329">Each project template may have additional options available.</span></span> <span data-ttu-id="8e657-330">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="8e657-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="8e657-331">console</span><span class="sxs-lookup"><span data-stu-id="8e657-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-332">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-333">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8e657-334">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-335">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-335">SDK version</span></span> | <span data-ttu-id="8e657-336">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-337">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-338">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8e657-339">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8e657-340">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="8e657-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8e657-341">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="8e657-341">Not supported for F#.</span></span> <span data-ttu-id="8e657-342">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="8e657-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8e657-343">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="8e657-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-344">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="8e657-345">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="8e657-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="8e657-346">classlib</span><span class="sxs-lookup"><span data-stu-id="8e657-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-347">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-348">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="8e657-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8e657-349">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="8e657-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8e657-350">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8e657-351">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="8e657-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8e657-352">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="8e657-352">Not supported for F#.</span></span> <span data-ttu-id="8e657-353">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="8e657-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8e657-354">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="8e657-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-355">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="8e657-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="8e657-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-357">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-358">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="8e657-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="8e657-359">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8e657-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8e657-360">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8e657-361">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="8e657-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="8e657-362">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="8e657-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-363">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="8e657-364">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="8e657-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8e657-365">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8e657-366">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="8e657-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="8e657-367">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="8e657-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-368">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="8e657-369">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="8e657-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-370">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-371">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="8e657-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="8e657-372">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8e657-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-373">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-374">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="8e657-375">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="8e657-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-376">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-377">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8e657-378">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-379">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-379">SDK version</span></span> | <span data-ttu-id="8e657-380">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-381">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-382">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="8e657-383">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-384">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="8e657-385">nunit</span><span class="sxs-lookup"><span data-stu-id="8e657-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-386">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="8e657-387">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-388">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-388">SDK version</span></span> | <span data-ttu-id="8e657-389">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-390">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-391">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8e657-392">2.2</span><span class="sxs-lookup"><span data-stu-id="8e657-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="8e657-393">2.1</span><span class="sxs-lookup"><span data-stu-id="8e657-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="8e657-394">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-395">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="8e657-396">страница</span><span class="sxs-lookup"><span data-stu-id="8e657-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="8e657-397">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="8e657-397">Namespace for the generated code.</span></span> <span data-ttu-id="8e657-398">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="8e657-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="8e657-399">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="8e657-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="8e657-400">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="8e657-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="8e657-401">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="8e657-401">Namespace for the generated code.</span></span> <span data-ttu-id="8e657-402">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="8e657-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="8e657-403">blazorserver</span><span class="sxs-lookup"><span data-stu-id="8e657-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8e657-404">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-404">The type of authentication to use.</span></span> <span data-ttu-id="8e657-405">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8e657-405">The possible values are:</span></span>

  - <span data-ttu-id="8e657-406">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8e657-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8e657-407">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="8e657-408">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8e657-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8e657-409">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="8e657-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8e657-410">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="8e657-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="8e657-411">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="8e657-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8e657-412">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e657-413">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-414">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8e657-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8e657-415">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e657-416">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="8e657-417">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="8e657-418">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="8e657-419">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="8e657-420">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8e657-421">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e657-422">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e657-423">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8e657-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8e657-424">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-424">The Client ID for this project.</span></span> <span data-ttu-id="8e657-425">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e657-426">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8e657-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8e657-427">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="8e657-427">The domain for the directory tenant.</span></span> <span data-ttu-id="8e657-428">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-429">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8e657-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8e657-430">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e657-431">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e657-432">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8e657-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="8e657-433">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="8e657-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8e657-434">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-435">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="8e657-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8e657-436">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="8e657-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e657-437">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-438">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8e657-439">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e657-439">Turns off HTTPS.</span></span> <span data-ttu-id="8e657-440">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="8e657-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8e657-441">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8e657-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e657-442">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-443">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="8e657-444">web</span><span class="sxs-lookup"><span data-stu-id="8e657-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-445">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-446">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-447">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="8e657-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8e657-448">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-449">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-449">SDK version</span></span> | <span data-ttu-id="8e657-450">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-451">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-452">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8e657-453">2.1</span><span class="sxs-lookup"><span data-stu-id="8e657-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="8e657-454">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8e657-455">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e657-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="8e657-456">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="8e657-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8e657-457">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-457">The type of authentication to use.</span></span> <span data-ttu-id="8e657-458">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8e657-458">The possible values are:</span></span>

  - <span data-ttu-id="8e657-459">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8e657-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8e657-460">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="8e657-461">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8e657-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8e657-462">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="8e657-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8e657-463">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="8e657-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="8e657-464">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="8e657-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8e657-465">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e657-466">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-467">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8e657-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8e657-468">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e657-469">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="8e657-470">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="8e657-471">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="8e657-472">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="8e657-473">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8e657-474">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e657-475">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e657-476">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8e657-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8e657-477">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-477">The Client ID for this project.</span></span> <span data-ttu-id="8e657-478">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e657-479">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8e657-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8e657-480">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="8e657-480">The domain for the directory tenant.</span></span> <span data-ttu-id="8e657-481">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-482">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8e657-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8e657-483">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e657-484">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e657-485">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8e657-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="8e657-486">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="8e657-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8e657-487">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-488">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="8e657-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8e657-489">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="8e657-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e657-490">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-491">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8e657-492">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e657-492">Turns off HTTPS.</span></span> <span data-ttu-id="8e657-493">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="8e657-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8e657-494">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8e657-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e657-495">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-496">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-497">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8e657-498">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-499">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-499">SDK version</span></span> | <span data-ttu-id="8e657-500">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-501">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-502">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="8e657-503">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="8e657-504">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="8e657-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="8e657-505">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="8e657-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="8e657-506">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="8e657-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="8e657-507">Параметр доступен, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8e657-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="8e657-508">angular, react</span><span class="sxs-lookup"><span data-stu-id="8e657-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8e657-509">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-509">The type of authentication to use.</span></span> <span data-ttu-id="8e657-510">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="8e657-511">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8e657-511">The possible values are:</span></span>

  - <span data-ttu-id="8e657-512">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8e657-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8e657-513">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-514">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-515">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8e657-516">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e657-516">Turns off HTTPS.</span></span> <span data-ttu-id="8e657-517">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="8e657-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8e657-518">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8e657-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e657-519">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-520">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-521">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-522">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="8e657-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8e657-523">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-524">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-524">SDK version</span></span> | <span data-ttu-id="8e657-525">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-526">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-527">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8e657-528">2.1</span><span class="sxs-lookup"><span data-stu-id="8e657-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="8e657-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="8e657-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-530">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-531">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-532">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="8e657-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8e657-533">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-534">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-534">SDK version</span></span> | <span data-ttu-id="8e657-535">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-536">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-537">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8e657-538">2.1</span><span class="sxs-lookup"><span data-stu-id="8e657-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="8e657-539">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8e657-540">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e657-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="8e657-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="8e657-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="8e657-542">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="8e657-543">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="8e657-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="8e657-544">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e657-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="8e657-545">webapi</span><span class="sxs-lookup"><span data-stu-id="8e657-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8e657-546">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-546">The type of authentication to use.</span></span> <span data-ttu-id="8e657-547">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8e657-547">The possible values are:</span></span>

  - <span data-ttu-id="8e657-548">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8e657-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8e657-549">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8e657-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8e657-550">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="8e657-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8e657-551">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="8e657-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8e657-552">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e657-553">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e657-554">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8e657-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8e657-555">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e657-556">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8e657-557">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e657-558">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e657-559">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8e657-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8e657-560">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="8e657-560">The Client ID for this project.</span></span> <span data-ttu-id="8e657-561">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8e657-562">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8e657-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8e657-563">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="8e657-563">The domain for the directory tenant.</span></span> <span data-ttu-id="8e657-564">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8e657-565">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8e657-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8e657-566">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="8e657-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e657-567">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e657-568">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8e657-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8e657-569">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="8e657-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e657-570">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8e657-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8e657-571">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="8e657-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8e657-572">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e657-572">Turns off HTTPS.</span></span> <span data-ttu-id="8e657-573">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="8e657-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8e657-574">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8e657-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8e657-575">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8e657-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e657-576">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8e657-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8e657-577">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8e657-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e657-578">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="8e657-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8e657-579">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="8e657-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8e657-580">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="8e657-580">SDK version</span></span> | <span data-ttu-id="8e657-581">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e657-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8e657-582">3.1</span><span class="sxs-lookup"><span data-stu-id="8e657-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8e657-583">3.0</span><span class="sxs-lookup"><span data-stu-id="8e657-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8e657-584">2.1</span><span class="sxs-lookup"><span data-stu-id="8e657-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="8e657-585">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="8e657-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="8e657-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="8e657-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="8e657-587">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="8e657-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="8e657-588">Примеры</span><span class="sxs-lookup"><span data-stu-id="8e657-588">Examples</span></span>

- <span data-ttu-id="8e657-589">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="8e657-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="8e657-590">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="8e657-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="8e657-591">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="8e657-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="8e657-592">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="8e657-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="8e657-593">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="8e657-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="8e657-594">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="8e657-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="8e657-595">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="8e657-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="8e657-596">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="8e657-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="8e657-597">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="8e657-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="8e657-598">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="8e657-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="8e657-599">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="8e657-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="8e657-600">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="8e657-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="8e657-601">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="8e657-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="8e657-602">См. также</span><span class="sxs-lookup"><span data-stu-id="8e657-602">See also</span></span>

- [<span data-ttu-id="8e657-603">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="8e657-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="8e657-604">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="8e657-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="8e657-605">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="8e657-605">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="8e657-606">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="8e657-606">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
