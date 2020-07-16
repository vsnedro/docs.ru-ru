---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
no-loc:
- Blazor
- WebAssembly
ms.date: 04/10/2020
ms.openlocfilehash: ec41b3b79ed5eded7c9124d3e4d95c658ee39580
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173124"
---
# <a name="dotnet-new"></a><span data-ttu-id="e1d89-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e1d89-103">dotnet new</span></span>

<span data-ttu-id="e1d89-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e1d89-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e1d89-105">name</span><span class="sxs-lookup"><span data-stu-id="e1d89-105">Name</span></span>

<span data-ttu-id="e1d89-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e1d89-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e1d89-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="e1d89-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e1d89-108">Description</span></span>

<span data-ttu-id="e1d89-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="e1d89-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="e1d89-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="e1d89-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="e1d89-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e1d89-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="e1d89-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="e1d89-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e1d89-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="e1d89-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e1d89-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e1d89-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="e1d89-116">Вы можете запустить `dotnet new --list` или `dotnet new -l`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e1d89-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="e1d89-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="e1d89-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="e1d89-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="e1d89-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="e1d89-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="e1d89-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="e1d89-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="e1d89-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="e1d89-122">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1d89-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="e1d89-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="e1d89-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="e1d89-124">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="e1d89-125">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="e1d89-125">Templates</span></span>                                    | <span data-ttu-id="e1d89-126">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="e1d89-126">Short name</span></span>                      | <span data-ttu-id="e1d89-127">Язык</span><span class="sxs-lookup"><span data-stu-id="e1d89-127">Language</span></span>     | <span data-ttu-id="e1d89-128">Tags</span><span class="sxs-lookup"><span data-stu-id="e1d89-128">Tags</span></span>                                  | <span data-ttu-id="e1d89-129">Введенный</span><span class="sxs-lookup"><span data-stu-id="e1d89-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="e1d89-130">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e1d89-130">Console Application</span></span>                          | [<span data-ttu-id="e1d89-131">Консоль</span><span class="sxs-lookup"><span data-stu-id="e1d89-131">console</span></span>](#console)             | <span data-ttu-id="e1d89-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e1d89-132">[C#], F#, VB</span></span> | <span data-ttu-id="e1d89-133">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="e1d89-133">Common/Console</span></span>                        | <span data-ttu-id="e1d89-134">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-134">1.0</span></span>        |
| <span data-ttu-id="e1d89-135">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="e1d89-135">Class library</span></span>                                | [<span data-ttu-id="e1d89-136">classlib</span><span class="sxs-lookup"><span data-stu-id="e1d89-136">classlib</span></span>](#classlib)           | <span data-ttu-id="e1d89-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e1d89-137">[C#], F#, VB</span></span> | <span data-ttu-id="e1d89-138">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="e1d89-138">Common/Library</span></span>                        | <span data-ttu-id="e1d89-139">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-139">1.0</span></span>        |
| <span data-ttu-id="e1d89-140">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-140">WPF Application</span></span>                              | [<span data-ttu-id="e1d89-141">wpf</span><span class="sxs-lookup"><span data-stu-id="e1d89-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="e1d89-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-142">[C#]</span></span>         | <span data-ttu-id="e1d89-143">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-143">Common/WPF</span></span>                            | <span data-ttu-id="e1d89-144">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-144">3.0</span></span>        |
| <span data-ttu-id="e1d89-145">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-145">WPF Class library</span></span>                            | [<span data-ttu-id="e1d89-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="e1d89-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="e1d89-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-147">[C#]</span></span>         | <span data-ttu-id="e1d89-148">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-148">Common/WPF</span></span>                            | <span data-ttu-id="e1d89-149">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-149">3.0</span></span>        |
| <span data-ttu-id="e1d89-150">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="e1d89-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="e1d89-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="e1d89-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-152">[C#]</span></span>         | <span data-ttu-id="e1d89-153">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-153">Common/WPF</span></span>                            | <span data-ttu-id="e1d89-154">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-154">3.0</span></span>        |
| <span data-ttu-id="e1d89-155">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="e1d89-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e1d89-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="e1d89-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-157">[C#]</span></span>         | <span data-ttu-id="e1d89-158">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e1d89-158">Common/WPF</span></span>                            | <span data-ttu-id="e1d89-159">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-159">3.0</span></span>        |
| <span data-ttu-id="e1d89-160">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e1d89-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="e1d89-161">winforms</span><span class="sxs-lookup"><span data-stu-id="e1d89-161">winforms</span></span>](#winforms)           | <span data-ttu-id="e1d89-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-162">[C#]</span></span>         | <span data-ttu-id="e1d89-163">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e1d89-163">Common/WinForms</span></span>                       | <span data-ttu-id="e1d89-164">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-164">3.0</span></span>        |
| <span data-ttu-id="e1d89-165">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e1d89-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="e1d89-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="e1d89-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="e1d89-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-167">[C#]</span></span>         | <span data-ttu-id="e1d89-168">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e1d89-168">Common/WinForms</span></span>                       | <span data-ttu-id="e1d89-169">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-169">3.0</span></span>        |
| <span data-ttu-id="e1d89-170">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="e1d89-170">Worker Service</span></span>                               | [<span data-ttu-id="e1d89-171">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="e1d89-171">worker</span></span>](#web-others)           | <span data-ttu-id="e1d89-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-172">[C#]</span></span>         | <span data-ttu-id="e1d89-173">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="e1d89-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="e1d89-174">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-174">3.0</span></span>        |
| <span data-ttu-id="e1d89-175">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="e1d89-175">Unit Test Project</span></span>                            | [<span data-ttu-id="e1d89-176">mstest</span><span class="sxs-lookup"><span data-stu-id="e1d89-176">mstest</span></span>](#test)                 | <span data-ttu-id="e1d89-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e1d89-177">[C#], F#, VB</span></span> | <span data-ttu-id="e1d89-178">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="e1d89-178">Test/MSTest</span></span>                           | <span data-ttu-id="e1d89-179">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-179">1.0</span></span>        |
| <span data-ttu-id="e1d89-180">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e1d89-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="e1d89-181">nunit</span><span class="sxs-lookup"><span data-stu-id="e1d89-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="e1d89-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e1d89-182">[C#], F#, VB</span></span> | <span data-ttu-id="e1d89-183">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="e1d89-183">Test/NUnit</span></span>                            | <span data-ttu-id="e1d89-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="e1d89-184">2.1.400</span></span>    |
| <span data-ttu-id="e1d89-185">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e1d89-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="e1d89-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e1d89-186">[C#], F#, VB</span></span> | <span data-ttu-id="e1d89-187">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="e1d89-187">Test/NUnit</span></span>                            | <span data-ttu-id="e1d89-188">2.2</span><span class="sxs-lookup"><span data-stu-id="e1d89-188">2.2</span></span>        |
| <span data-ttu-id="e1d89-189">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="e1d89-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="e1d89-190">xunit</span><span class="sxs-lookup"><span data-stu-id="e1d89-190">xunit</span></span>](#test)                  | <span data-ttu-id="e1d89-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e1d89-191">[C#], F#, VB</span></span> | <span data-ttu-id="e1d89-192">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="e1d89-192">Test/xUnit</span></span>                            | <span data-ttu-id="e1d89-193">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-193">1.0</span></span>        |
| <span data-ttu-id="e1d89-194">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="e1d89-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="e1d89-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-195">[C#]</span></span>         | <span data-ttu-id="e1d89-196">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e1d89-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="e1d89-197">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-197">3.0</span></span>        |
| <span data-ttu-id="e1d89-198">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="e1d89-198">Razor Page</span></span>                                   | [<span data-ttu-id="e1d89-199">page</span><span class="sxs-lookup"><span data-stu-id="e1d89-199">page</span></span>](#page)                   | <span data-ttu-id="e1d89-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-200">[C#]</span></span>         | <span data-ttu-id="e1d89-201">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e1d89-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="e1d89-202">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-202">2.0</span></span>        |
| <span data-ttu-id="e1d89-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e1d89-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="e1d89-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="e1d89-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="e1d89-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-205">[C#]</span></span>         | <span data-ttu-id="e1d89-206">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e1d89-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="e1d89-207">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-207">2.0</span></span>        |
| <span data-ttu-id="e1d89-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e1d89-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="e1d89-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-209">[C#]</span></span>         | <span data-ttu-id="e1d89-210">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e1d89-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="e1d89-211">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-211">2.0</span></span>        |
| <span data-ttu-id="e1d89-212">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="e1d89-212">Blazor Server App</span></span>                            | [<span data-ttu-id="e1d89-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e1d89-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="e1d89-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-214">[C#]</span></span>         | <span data-ttu-id="e1d89-215">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="e1d89-215">Web/Blazor</span></span>                            | <span data-ttu-id="e1d89-216">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-216">3.0</span></span>        |
| <span data-ttu-id="e1d89-217">Приложение WebAssembly Blazor</span><span class="sxs-lookup"><span data-stu-id="e1d89-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="e1d89-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-218">[C#]</span></span>         | <span data-ttu-id="e1d89-219">Веб/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="e1d89-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="e1d89-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="e1d89-220">3.1.300</span></span>    |
| <span data-ttu-id="e1d89-221">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e1d89-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="e1d89-222">web</span><span class="sxs-lookup"><span data-stu-id="e1d89-222">web</span></span>](#web)                     | <span data-ttu-id="e1d89-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e1d89-223">[C#], F#</span></span>     | <span data-ttu-id="e1d89-224">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="e1d89-224">Web/Empty</span></span>                             | <span data-ttu-id="e1d89-225">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-225">1.0</span></span>        |
| <span data-ttu-id="e1d89-226">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e1d89-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="e1d89-227">mvc</span><span class="sxs-lookup"><span data-stu-id="e1d89-227">mvc</span></span>](#web-options)             | <span data-ttu-id="e1d89-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e1d89-228">[C#], F#</span></span>     | <span data-ttu-id="e1d89-229">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="e1d89-229">Web/MVC</span></span>                               | <span data-ttu-id="e1d89-230">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-230">1.0</span></span>        |
| <span data-ttu-id="e1d89-231">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e1d89-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="e1d89-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="e1d89-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="e1d89-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-233">[C#]</span></span>         | <span data-ttu-id="e1d89-234">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="e1d89-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="e1d89-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="e1d89-236">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="e1d89-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="e1d89-237">angular</span><span class="sxs-lookup"><span data-stu-id="e1d89-237">angular</span></span>](#spa)                 | <span data-ttu-id="e1d89-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-238">[C#]</span></span>         | <span data-ttu-id="e1d89-239">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e1d89-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e1d89-240">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-240">2.0</span></span>        |
| <span data-ttu-id="e1d89-241">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="e1d89-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="e1d89-242">react</span><span class="sxs-lookup"><span data-stu-id="e1d89-242">react</span></span>](#spa)                   | <span data-ttu-id="e1d89-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-243">[C#]</span></span>         | <span data-ttu-id="e1d89-244">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e1d89-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e1d89-245">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-245">2.0</span></span>        |
| <span data-ttu-id="e1d89-246">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="e1d89-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="e1d89-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="e1d89-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="e1d89-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-248">[C#]</span></span>         | <span data-ttu-id="e1d89-249">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e1d89-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e1d89-250">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-250">2.0</span></span>        |
| <span data-ttu-id="e1d89-251">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e1d89-251">Razor Class Library</span></span>                          | [<span data-ttu-id="e1d89-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e1d89-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="e1d89-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-253">[C#]</span></span>         | <span data-ttu-id="e1d89-254">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e1d89-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="e1d89-255">2.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-255">2.1</span></span>        |
| <span data-ttu-id="e1d89-256">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e1d89-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="e1d89-257">webapi</span><span class="sxs-lookup"><span data-stu-id="e1d89-257">webapi</span></span>](#webapi)               | <span data-ttu-id="e1d89-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e1d89-258">[C#], F#</span></span>     | <span data-ttu-id="e1d89-259">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="e1d89-259">Web/WebAPI</span></span>                            | <span data-ttu-id="e1d89-260">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-260">1.0</span></span>        |
| <span data-ttu-id="e1d89-261">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e1d89-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="e1d89-262">grpc</span><span class="sxs-lookup"><span data-stu-id="e1d89-262">grpc</span></span>](#web-others)             | <span data-ttu-id="e1d89-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="e1d89-263">[C#]</span></span>         | <span data-ttu-id="e1d89-264">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="e1d89-264">Web/gRPC</span></span>                              | <span data-ttu-id="e1d89-265">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-265">3.0</span></span>        |
| <span data-ttu-id="e1d89-266">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="e1d89-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="e1d89-267">Config</span><span class="sxs-lookup"><span data-stu-id="e1d89-267">Config</span></span>                                | <span data-ttu-id="e1d89-268">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-268">3.0</span></span>        |
| <span data-ttu-id="e1d89-269">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="e1d89-269">global.json file</span></span>                             | [<span data-ttu-id="e1d89-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="e1d89-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="e1d89-271">Config</span><span class="sxs-lookup"><span data-stu-id="e1d89-271">Config</span></span>                                | <span data-ttu-id="e1d89-272">2.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-272">2.0</span></span>        |
| <span data-ttu-id="e1d89-273">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="e1d89-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="e1d89-274">Config</span><span class="sxs-lookup"><span data-stu-id="e1d89-274">Config</span></span>                                | <span data-ttu-id="e1d89-275">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-275">1.0</span></span>        |
| <span data-ttu-id="e1d89-276">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="e1d89-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="e1d89-277">Config</span><span class="sxs-lookup"><span data-stu-id="e1d89-277">Config</span></span>                                | <span data-ttu-id="e1d89-278">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-278">3.0</span></span>        |
| <span data-ttu-id="e1d89-279">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="e1d89-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="e1d89-280">Config</span><span class="sxs-lookup"><span data-stu-id="e1d89-280">Config</span></span>                                | <span data-ttu-id="e1d89-281">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-281">1.0</span></span>        |
| <span data-ttu-id="e1d89-282">Файл решения</span><span class="sxs-lookup"><span data-stu-id="e1d89-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="e1d89-283">Решение</span><span class="sxs-lookup"><span data-stu-id="e1d89-283">Solution</span></span>                              | <span data-ttu-id="e1d89-284">1.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-284">1.0</span></span>        |
| <span data-ttu-id="e1d89-285">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="e1d89-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="e1d89-286">proto</span><span class="sxs-lookup"><span data-stu-id="e1d89-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="e1d89-287">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="e1d89-287">Web/gRPC</span></span>                              | <span data-ttu-id="e1d89-288">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="e1d89-289">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1d89-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="e1d89-290">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="e1d89-291">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e1d89-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="e1d89-292">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="e1d89-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e1d89-293">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="e1d89-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e1d89-294">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="e1d89-294">Prints out help for the command.</span></span> <span data-ttu-id="e1d89-295">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="e1d89-296">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="e1d89-297">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e1d89-298">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e1d89-299">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="e1d89-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="e1d89-300">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="e1d89-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="e1d89-301">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="e1d89-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="e1d89-302">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="e1d89-303">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e1d89-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="e1d89-304">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e1d89-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="e1d89-305">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-305">The language of the template to create.</span></span> <span data-ttu-id="e1d89-306">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e1d89-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e1d89-307">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e1d89-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e1d89-308">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="e1d89-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e1d89-309">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="e1d89-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="e1d89-310">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="e1d89-311">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e1d89-311">The name for the created output.</span></span> <span data-ttu-id="e1d89-312">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d89-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="e1d89-313">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="e1d89-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="e1d89-314">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="e1d89-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e1d89-315">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e1d89-315">Location to place the generated output.</span></span> <span data-ttu-id="e1d89-316">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e1d89-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="e1d89-317">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="e1d89-317">Filters templates based on available types.</span></span> <span data-ttu-id="e1d89-318">Предопределенные значения: `project`, `item` и `other`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="e1d89-319">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e1d89-320">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e1d89-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="e1d89-321">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="e1d89-322">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="e1d89-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e1d89-323">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="e1d89-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e1d89-324">Например, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="e1d89-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="e1d89-325">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d89-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="e1d89-326">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="e1d89-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="e1d89-327">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="e1d89-328">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e1d89-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="e1d89-329">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="e1d89-330">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="e1d89-330">Template options</span></span>

<span data-ttu-id="e1d89-331">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="e1d89-331">Each project template may have additional options available.</span></span> <span data-ttu-id="e1d89-332">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="e1d89-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="e1d89-333">console</span><span class="sxs-lookup"><span data-stu-id="e1d89-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-334">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-335">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e1d89-336">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-337">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-337">SDK version</span></span> | <span data-ttu-id="e1d89-338">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-339">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-340">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e1d89-341">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e1d89-342">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e1d89-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e1d89-343">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="e1d89-343">Not supported for F#.</span></span> <span data-ttu-id="e1d89-344">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e1d89-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e1d89-345">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e1d89-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-346">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="e1d89-347">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e1d89-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="e1d89-348">classlib</span><span class="sxs-lookup"><span data-stu-id="e1d89-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-349">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-350">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="e1d89-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e1d89-351">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e1d89-352">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e1d89-353">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e1d89-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e1d89-354">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="e1d89-354">Not supported for F#.</span></span> <span data-ttu-id="e1d89-355">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e1d89-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e1d89-356">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e1d89-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-357">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="e1d89-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e1d89-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-359">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-360">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e1d89-361">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e1d89-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e1d89-362">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e1d89-363">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e1d89-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e1d89-364">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e1d89-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-365">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="e1d89-366">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="e1d89-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e1d89-367">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e1d89-368">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e1d89-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e1d89-369">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e1d89-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-370">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="e1d89-371">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="e1d89-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-372">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-373">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e1d89-374">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e1d89-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-375">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-376">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="e1d89-377">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="e1d89-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-378">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-379">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e1d89-380">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-381">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-381">SDK version</span></span> | <span data-ttu-id="e1d89-382">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-383">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-384">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e1d89-385">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-386">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="e1d89-387">nunit</span><span class="sxs-lookup"><span data-stu-id="e1d89-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-388">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e1d89-389">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-390">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-390">SDK version</span></span> | <span data-ttu-id="e1d89-391">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-392">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-393">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e1d89-394">2.2</span><span class="sxs-lookup"><span data-stu-id="e1d89-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="e1d89-395">2.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e1d89-396">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-397">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="e1d89-398">страница</span><span class="sxs-lookup"><span data-stu-id="e1d89-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e1d89-399">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="e1d89-399">Namespace for the generated code.</span></span> <span data-ttu-id="e1d89-400">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="e1d89-401">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="e1d89-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="e1d89-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="e1d89-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e1d89-403">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="e1d89-403">Namespace for the generated code.</span></span> <span data-ttu-id="e1d89-404">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="e1d89-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e1d89-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e1d89-406">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-406">The type of authentication to use.</span></span> <span data-ttu-id="e1d89-407">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e1d89-407">The possible values are:</span></span>

  - <span data-ttu-id="e1d89-408">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e1d89-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e1d89-409">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e1d89-410">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e1d89-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e1d89-411">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d89-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e1d89-412">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e1d89-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e1d89-413">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e1d89-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e1d89-414">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e1d89-415">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-416">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e1d89-417">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e1d89-418">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e1d89-419">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="e1d89-420">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e1d89-421">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e1d89-422">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e1d89-423">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e1d89-424">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e1d89-425">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e1d89-426">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-426">The Client ID for this project.</span></span> <span data-ttu-id="e1d89-427">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e1d89-428">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e1d89-429">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d89-429">The domain for the directory tenant.</span></span> <span data-ttu-id="e1d89-430">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-431">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e1d89-432">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e1d89-433">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e1d89-434">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e1d89-435">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e1d89-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e1d89-436">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-437">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e1d89-438">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e1d89-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e1d89-439">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-440">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e1d89-441">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e1d89-441">Turns off HTTPS.</span></span> <span data-ttu-id="e1d89-442">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e1d89-443">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e1d89-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e1d89-444">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-445">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="e1d89-446">web</span><span class="sxs-lookup"><span data-stu-id="e1d89-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-447">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-448">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-449">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e1d89-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e1d89-450">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-451">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-451">SDK version</span></span> | <span data-ttu-id="e1d89-452">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-453">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-454">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e1d89-455">2.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e1d89-456">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e1d89-457">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e1d89-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="e1d89-458">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="e1d89-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e1d89-459">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-459">The type of authentication to use.</span></span> <span data-ttu-id="e1d89-460">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e1d89-460">The possible values are:</span></span>

  - <span data-ttu-id="e1d89-461">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e1d89-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e1d89-462">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e1d89-463">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e1d89-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e1d89-464">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d89-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e1d89-465">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e1d89-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e1d89-466">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e1d89-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e1d89-467">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e1d89-468">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-469">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e1d89-470">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e1d89-471">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e1d89-472">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="e1d89-473">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e1d89-474">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e1d89-475">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e1d89-476">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e1d89-477">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e1d89-478">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e1d89-479">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-479">The Client ID for this project.</span></span> <span data-ttu-id="e1d89-480">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e1d89-481">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e1d89-482">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d89-482">The domain for the directory tenant.</span></span> <span data-ttu-id="e1d89-483">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-484">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e1d89-485">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e1d89-486">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e1d89-487">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e1d89-488">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e1d89-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e1d89-489">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-490">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e1d89-491">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e1d89-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e1d89-492">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-493">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e1d89-494">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e1d89-494">Turns off HTTPS.</span></span> <span data-ttu-id="e1d89-495">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="e1d89-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e1d89-496">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e1d89-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e1d89-497">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-498">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-499">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e1d89-500">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-501">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-501">SDK version</span></span> | <span data-ttu-id="e1d89-502">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-503">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-504">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="e1d89-505">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="e1d89-506">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="e1d89-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="e1d89-507">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e1d89-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="e1d89-508">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="e1d89-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="e1d89-509">Параметр доступен начиная с пакета SDK для .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="e1d89-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="e1d89-510">angular, react</span><span class="sxs-lookup"><span data-stu-id="e1d89-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e1d89-511">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-511">The type of authentication to use.</span></span> <span data-ttu-id="e1d89-512">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="e1d89-513">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e1d89-513">The possible values are:</span></span>

  - <span data-ttu-id="e1d89-514">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e1d89-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e1d89-515">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-516">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-517">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e1d89-518">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e1d89-518">Turns off HTTPS.</span></span> <span data-ttu-id="e1d89-519">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e1d89-520">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e1d89-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e1d89-521">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-522">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-523">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-524">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e1d89-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e1d89-525">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-526">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-526">SDK version</span></span> | <span data-ttu-id="e1d89-527">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-528">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-529">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e1d89-530">2.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="e1d89-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="e1d89-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-532">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-533">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-534">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e1d89-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e1d89-535">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-536">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-536">SDK version</span></span> | <span data-ttu-id="e1d89-537">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-538">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-539">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e1d89-540">2.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="e1d89-541">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e1d89-542">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e1d89-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="e1d89-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e1d89-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="e1d89-544">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="e1d89-545">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e1d89-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="e1d89-546">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e1d89-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="e1d89-547">webapi</span><span class="sxs-lookup"><span data-stu-id="e1d89-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e1d89-548">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-548">The type of authentication to use.</span></span> <span data-ttu-id="e1d89-549">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e1d89-549">The possible values are:</span></span>

  - <span data-ttu-id="e1d89-550">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e1d89-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e1d89-551">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e1d89-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e1d89-552">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d89-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e1d89-553">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e1d89-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e1d89-554">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e1d89-555">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e1d89-556">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e1d89-557">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e1d89-558">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e1d89-559">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e1d89-560">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e1d89-561">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e1d89-562">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e1d89-562">The Client ID for this project.</span></span> <span data-ttu-id="e1d89-563">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e1d89-564">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e1d89-565">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d89-565">The domain for the directory tenant.</span></span> <span data-ttu-id="e1d89-566">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e1d89-567">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e1d89-568">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e1d89-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e1d89-569">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e1d89-570">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e1d89-571">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e1d89-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e1d89-572">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e1d89-573">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e1d89-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e1d89-574">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e1d89-574">Turns off HTTPS.</span></span> <span data-ttu-id="e1d89-575">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e1d89-576">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d89-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e1d89-577">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e1d89-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e1d89-578">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e1d89-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e1d89-579">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e1d89-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e1d89-580">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e1d89-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e1d89-581">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e1d89-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e1d89-582">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e1d89-582">SDK version</span></span> | <span data-ttu-id="e1d89-583">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1d89-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e1d89-584">3.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e1d89-585">3.0</span><span class="sxs-lookup"><span data-stu-id="e1d89-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e1d89-586">2.1</span><span class="sxs-lookup"><span data-stu-id="e1d89-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e1d89-587">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e1d89-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="e1d89-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="e1d89-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="e1d89-589">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e1d89-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="e1d89-590">Примеры</span><span class="sxs-lookup"><span data-stu-id="e1d89-590">Examples</span></span>

- <span data-ttu-id="e1d89-591">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="e1d89-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="e1d89-592">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="e1d89-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="e1d89-593">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="e1d89-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="e1d89-594">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="e1d89-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="e1d89-595">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="e1d89-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="e1d89-596">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="e1d89-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="e1d89-597">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="e1d89-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="e1d89-598">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="e1d89-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="e1d89-599">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="e1d89-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="e1d89-600">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="e1d89-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="e1d89-601">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="e1d89-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="e1d89-602">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="e1d89-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="e1d89-603">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="e1d89-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="e1d89-604">См. также</span><span class="sxs-lookup"><span data-stu-id="e1d89-604">See also</span></span>

- [<span data-ttu-id="e1d89-605">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e1d89-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="e1d89-606">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="e1d89-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="e1d89-607">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="e1d89-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="e1d89-608">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e1d89-608">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
