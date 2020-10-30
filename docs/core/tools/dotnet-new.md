---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/01/2020
ms.openlocfilehash: 4a4c8e2806fee663b5f6aa255a6f24250a072a85
ms.sourcegitcommit: 532b03d5bbab764d63356193b04cd2281bc01239
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2020
ms.locfileid: "92526611"
---
# <a name="dotnet-new"></a><span data-ttu-id="23242-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="23242-103">dotnet new</span></span>

<span data-ttu-id="23242-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="23242-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="23242-105">name</span><span class="sxs-lookup"><span data-stu-id="23242-105">Name</span></span>

<span data-ttu-id="23242-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="23242-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="23242-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="23242-108">Описание</span><span class="sxs-lookup"><span data-stu-id="23242-108">Description</span></span>

<span data-ttu-id="23242-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="23242-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="23242-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="23242-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="23242-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="23242-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="23242-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="23242-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="23242-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="23242-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="23242-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="23242-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="23242-116">Вы можете запустить `dotnet new --list` или `dotnet new -l`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="23242-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="23242-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="23242-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="23242-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="23242-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="23242-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="23242-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="23242-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="23242-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="23242-122">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="23242-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="23242-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="23242-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="23242-124">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="23242-125">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="23242-125">Templates</span></span>                                    | <span data-ttu-id="23242-126">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="23242-126">Short name</span></span>                      | <span data-ttu-id="23242-127">Язык</span><span class="sxs-lookup"><span data-stu-id="23242-127">Language</span></span>     | <span data-ttu-id="23242-128">Tags</span><span class="sxs-lookup"><span data-stu-id="23242-128">Tags</span></span>                                  | <span data-ttu-id="23242-129">Введенный</span><span class="sxs-lookup"><span data-stu-id="23242-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="23242-130">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="23242-130">Console Application</span></span>                          | [<span data-ttu-id="23242-131">Консоль</span><span class="sxs-lookup"><span data-stu-id="23242-131">console</span></span>](#console)             | <span data-ttu-id="23242-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="23242-132">[C#], F#, VB</span></span> | <span data-ttu-id="23242-133">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="23242-133">Common/Console</span></span>                        | <span data-ttu-id="23242-134">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-134">1.0</span></span>        |
| <span data-ttu-id="23242-135">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="23242-135">Class library</span></span>                                | [<span data-ttu-id="23242-136">classlib</span><span class="sxs-lookup"><span data-stu-id="23242-136">classlib</span></span>](#classlib)           | <span data-ttu-id="23242-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="23242-137">[C#], F#, VB</span></span> | <span data-ttu-id="23242-138">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="23242-138">Common/Library</span></span>                        | <span data-ttu-id="23242-139">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-139">1.0</span></span>        |
| <span data-ttu-id="23242-140">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="23242-140">WPF Application</span></span>                              | [<span data-ttu-id="23242-141">wpf</span><span class="sxs-lookup"><span data-stu-id="23242-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="23242-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="23242-142">[C#], VB</span></span>     | <span data-ttu-id="23242-143">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="23242-143">Common/WPF</span></span>                            | <span data-ttu-id="23242-144">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="23242-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="23242-145">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="23242-145">WPF Class library</span></span>                            | [<span data-ttu-id="23242-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="23242-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="23242-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="23242-147">[C#], VB</span></span>     | <span data-ttu-id="23242-148">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="23242-148">Common/WPF</span></span>                            | <span data-ttu-id="23242-149">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="23242-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="23242-150">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="23242-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="23242-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="23242-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="23242-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="23242-152">[C#], VB</span></span>     | <span data-ttu-id="23242-153">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="23242-153">Common/WPF</span></span>                            | <span data-ttu-id="23242-154">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="23242-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="23242-155">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="23242-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="23242-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="23242-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="23242-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="23242-157">[C#], VB</span></span>     | <span data-ttu-id="23242-158">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="23242-158">Common/WPF</span></span>                            | <span data-ttu-id="23242-159">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="23242-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="23242-160">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="23242-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="23242-161">winforms</span><span class="sxs-lookup"><span data-stu-id="23242-161">winforms</span></span>](#winforms)           | <span data-ttu-id="23242-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="23242-162">[C#], VB</span></span>     | <span data-ttu-id="23242-163">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="23242-163">Common/WinForms</span></span>                       | <span data-ttu-id="23242-164">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="23242-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="23242-165">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="23242-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="23242-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="23242-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="23242-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="23242-167">[C#], VB</span></span>     | <span data-ttu-id="23242-168">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="23242-168">Common/WinForms</span></span>                       | <span data-ttu-id="23242-169">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="23242-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="23242-170">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="23242-170">Worker Service</span></span>                               | [<span data-ttu-id="23242-171">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="23242-171">worker</span></span>](#web-others)           | <span data-ttu-id="23242-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-172">[C#]</span></span>         | <span data-ttu-id="23242-173">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="23242-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="23242-174">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-174">3.0</span></span>        |
| <span data-ttu-id="23242-175">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="23242-175">Unit Test Project</span></span>                            | [<span data-ttu-id="23242-176">mstest</span><span class="sxs-lookup"><span data-stu-id="23242-176">mstest</span></span>](#test)                 | <span data-ttu-id="23242-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="23242-177">[C#], F#, VB</span></span> | <span data-ttu-id="23242-178">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="23242-178">Test/MSTest</span></span>                           | <span data-ttu-id="23242-179">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-179">1.0</span></span>        |
| <span data-ttu-id="23242-180">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="23242-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="23242-181">nunit</span><span class="sxs-lookup"><span data-stu-id="23242-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="23242-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="23242-182">[C#], F#, VB</span></span> | <span data-ttu-id="23242-183">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="23242-183">Test/NUnit</span></span>                            | <span data-ttu-id="23242-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="23242-184">2.1.400</span></span>    |
| <span data-ttu-id="23242-185">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="23242-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="23242-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="23242-186">[C#], F#, VB</span></span> | <span data-ttu-id="23242-187">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="23242-187">Test/NUnit</span></span>                            | <span data-ttu-id="23242-188">2.2</span><span class="sxs-lookup"><span data-stu-id="23242-188">2.2</span></span>        |
| <span data-ttu-id="23242-189">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="23242-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="23242-190">xunit</span><span class="sxs-lookup"><span data-stu-id="23242-190">xunit</span></span>](#test)                  | <span data-ttu-id="23242-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="23242-191">[C#], F#, VB</span></span> | <span data-ttu-id="23242-192">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="23242-192">Test/xUnit</span></span>                            | <span data-ttu-id="23242-193">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-193">1.0</span></span>        |
| <span data-ttu-id="23242-194">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="23242-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="23242-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-195">[C#]</span></span>         | <span data-ttu-id="23242-196">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="23242-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="23242-197">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-197">3.0</span></span>        |
| <span data-ttu-id="23242-198">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="23242-198">Razor Page</span></span>                                   | [<span data-ttu-id="23242-199">page</span><span class="sxs-lookup"><span data-stu-id="23242-199">page</span></span>](#page)                   | <span data-ttu-id="23242-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-200">[C#]</span></span>         | <span data-ttu-id="23242-201">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="23242-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="23242-202">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-202">2.0</span></span>        |
| <span data-ttu-id="23242-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="23242-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="23242-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="23242-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="23242-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-205">[C#]</span></span>         | <span data-ttu-id="23242-206">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="23242-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="23242-207">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-207">2.0</span></span>        |
| <span data-ttu-id="23242-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="23242-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="23242-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-209">[C#]</span></span>         | <span data-ttu-id="23242-210">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="23242-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="23242-211">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-211">2.0</span></span>        |
| <span data-ttu-id="23242-212">Серверное приложение :::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="23242-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="23242-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="23242-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="23242-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-214">[C#]</span></span>         | <span data-ttu-id="23242-215">Веб/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="23242-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="23242-216">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-216">3.0</span></span>        |
| <span data-ttu-id="23242-217">Приложение :::no-loc(WebAssembly)::: :::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="23242-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="23242-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-218">[C#]</span></span>         | <span data-ttu-id="23242-219">Веб/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="23242-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="23242-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="23242-220">3.1.300</span></span>    |
| <span data-ttu-id="23242-221">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="23242-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="23242-222">web</span><span class="sxs-lookup"><span data-stu-id="23242-222">web</span></span>](#web)                     | <span data-ttu-id="23242-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="23242-223">[C#], F#</span></span>     | <span data-ttu-id="23242-224">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="23242-224">Web/Empty</span></span>                             | <span data-ttu-id="23242-225">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-225">1.0</span></span>        |
| <span data-ttu-id="23242-226">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="23242-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="23242-227">mvc</span><span class="sxs-lookup"><span data-stu-id="23242-227">mvc</span></span>](#web-options)             | <span data-ttu-id="23242-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="23242-228">[C#], F#</span></span>     | <span data-ttu-id="23242-229">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="23242-229">Web/MVC</span></span>                               | <span data-ttu-id="23242-230">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-230">1.0</span></span>        |
| <span data-ttu-id="23242-231">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="23242-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="23242-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="23242-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="23242-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-233">[C#]</span></span>         | <span data-ttu-id="23242-234">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="23242-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="23242-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="23242-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="23242-236">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="23242-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="23242-237">angular</span><span class="sxs-lookup"><span data-stu-id="23242-237">angular</span></span>](#spa)                 | <span data-ttu-id="23242-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-238">[C#]</span></span>         | <span data-ttu-id="23242-239">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="23242-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="23242-240">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-240">2.0</span></span>        |
| <span data-ttu-id="23242-241">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="23242-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="23242-242">react</span><span class="sxs-lookup"><span data-stu-id="23242-242">react</span></span>](#spa)                   | <span data-ttu-id="23242-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-243">[C#]</span></span>         | <span data-ttu-id="23242-244">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="23242-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="23242-245">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-245">2.0</span></span>        |
| <span data-ttu-id="23242-246">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="23242-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="23242-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="23242-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="23242-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-248">[C#]</span></span>         | <span data-ttu-id="23242-249">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="23242-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="23242-250">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-250">2.0</span></span>        |
| <span data-ttu-id="23242-251">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="23242-251">Razor Class Library</span></span>                          | [<span data-ttu-id="23242-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="23242-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="23242-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-253">[C#]</span></span>         | <span data-ttu-id="23242-254">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="23242-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="23242-255">2.1</span><span class="sxs-lookup"><span data-stu-id="23242-255">2.1</span></span>        |
| <span data-ttu-id="23242-256">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="23242-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="23242-257">webapi</span><span class="sxs-lookup"><span data-stu-id="23242-257">webapi</span></span>](#webapi)               | <span data-ttu-id="23242-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="23242-258">[C#], F#</span></span>     | <span data-ttu-id="23242-259">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="23242-259">Web/WebAPI</span></span>                            | <span data-ttu-id="23242-260">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-260">1.0</span></span>        |
| <span data-ttu-id="23242-261">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="23242-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="23242-262">grpc</span><span class="sxs-lookup"><span data-stu-id="23242-262">grpc</span></span>](#web-others)             | <span data-ttu-id="23242-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="23242-263">[C#]</span></span>         | <span data-ttu-id="23242-264">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="23242-264">Web/gRPC</span></span>                              | <span data-ttu-id="23242-265">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-265">3.0</span></span>        |
| <span data-ttu-id="23242-266">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="23242-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="23242-267">Config</span><span class="sxs-lookup"><span data-stu-id="23242-267">Config</span></span>                                | <span data-ttu-id="23242-268">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-268">3.0</span></span>        |
| <span data-ttu-id="23242-269">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="23242-269">global.json file</span></span>                             | [<span data-ttu-id="23242-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="23242-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="23242-271">Config</span><span class="sxs-lookup"><span data-stu-id="23242-271">Config</span></span>                                | <span data-ttu-id="23242-272">2.0</span><span class="sxs-lookup"><span data-stu-id="23242-272">2.0</span></span>        |
| <span data-ttu-id="23242-273">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="23242-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="23242-274">Config</span><span class="sxs-lookup"><span data-stu-id="23242-274">Config</span></span>                                | <span data-ttu-id="23242-275">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-275">1.0</span></span>        |
| <span data-ttu-id="23242-276">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="23242-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="23242-277">Config</span><span class="sxs-lookup"><span data-stu-id="23242-277">Config</span></span>                                | <span data-ttu-id="23242-278">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-278">3.0</span></span>        |
| <span data-ttu-id="23242-279">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="23242-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="23242-280">Config</span><span class="sxs-lookup"><span data-stu-id="23242-280">Config</span></span>                                | <span data-ttu-id="23242-281">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-281">1.0</span></span>        |
| <span data-ttu-id="23242-282">Файл решения</span><span class="sxs-lookup"><span data-stu-id="23242-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="23242-283">Решение</span><span class="sxs-lookup"><span data-stu-id="23242-283">Solution</span></span>                              | <span data-ttu-id="23242-284">1.0</span><span class="sxs-lookup"><span data-stu-id="23242-284">1.0</span></span>        |
| <span data-ttu-id="23242-285">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="23242-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="23242-286">proto</span><span class="sxs-lookup"><span data-stu-id="23242-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="23242-287">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="23242-287">Web/gRPC</span></span>                              | <span data-ttu-id="23242-288">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="23242-289">Параметры</span><span class="sxs-lookup"><span data-stu-id="23242-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="23242-290">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="23242-291">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="23242-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="23242-292">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="23242-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="23242-293">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="23242-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="23242-294">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="23242-294">Prints out help for the command.</span></span> <span data-ttu-id="23242-295">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="23242-296">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="23242-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="23242-297">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="23242-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="23242-298">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="23242-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="23242-299">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="23242-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="23242-300">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="23242-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="23242-301">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="23242-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="23242-302">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="23242-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="23242-303">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="23242-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="23242-304">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="23242-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="23242-305">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-305">The language of the template to create.</span></span> <span data-ttu-id="23242-306">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="23242-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="23242-307">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="23242-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="23242-308">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="23242-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="23242-309">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="23242-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="23242-310">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="23242-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="23242-311">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="23242-311">The name for the created output.</span></span> <span data-ttu-id="23242-312">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="23242-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="23242-313">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="23242-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="23242-314">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="23242-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="23242-315">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="23242-315">Location to place the generated output.</span></span> <span data-ttu-id="23242-316">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="23242-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="23242-317">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="23242-317">Filters templates based on available types.</span></span> <span data-ttu-id="23242-318">Предопределенные значения: `project` и `item`.</span><span class="sxs-lookup"><span data-stu-id="23242-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="23242-319">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="23242-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="23242-320">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="23242-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="23242-321">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="23242-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="23242-322">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="23242-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="23242-323">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="23242-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="23242-324">Например, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp*  — нет.</span><span class="sxs-lookup"><span data-stu-id="23242-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="23242-325">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="23242-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="23242-326">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="23242-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="23242-327">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="23242-328">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="23242-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="23242-329">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="23242-330">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="23242-330">Template options</span></span>

<span data-ttu-id="23242-331">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="23242-331">Each project template may have additional options available.</span></span> <span data-ttu-id="23242-332">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="23242-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="23242-333">console</span><span class="sxs-lookup"><span data-stu-id="23242-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="23242-334">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-335">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="23242-336">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-337">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-337">SDK version</span></span> | <span data-ttu-id="23242-338">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-339">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-340">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="23242-341">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="23242-342">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="23242-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="23242-343">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="23242-343">Not supported for F#.</span></span> <span data-ttu-id="23242-344">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="23242-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="23242-345">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="23242-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-346">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="23242-347">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="23242-347">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="23242-348">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-348">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="23242-349">classlib</span><span class="sxs-lookup"><span data-stu-id="23242-349">classlib</span></span>

- <span data-ttu-id="23242-350">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-350">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="23242-351">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-351">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-352">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="23242-352">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="23242-353">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="23242-353">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="23242-354">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-354">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="23242-355">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="23242-355">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="23242-356">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="23242-356">Not supported for F#.</span></span> <span data-ttu-id="23242-357">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="23242-357">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="23242-358">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="23242-358">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-359">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-359">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-360">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-360">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="23242-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="23242-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="23242-362">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-362">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="23242-363">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-363">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-364">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="23242-364">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="23242-365">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="23242-365">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="23242-366">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-366">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="23242-367">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="23242-367">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="23242-368">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="23242-368">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-369">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-369">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-370">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-370">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="23242-371">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="23242-371">winforms, winformslib</span></span>

- <span data-ttu-id="23242-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="23242-373">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-373">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="23242-374">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="23242-374">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="23242-375">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="23242-375">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-376">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-376">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-377">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-377">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="23242-378">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="23242-378">worker, grpc</span></span>

- <span data-ttu-id="23242-379">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-379">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="23242-380">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-380">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-381">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="23242-381">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="23242-382">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="23242-382">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="23242-383">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-383">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-384">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-384">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-385">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-385">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="23242-386">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="23242-386">mstest, xunit</span></span>

- <span data-ttu-id="23242-387">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-387">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="23242-388">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-389">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-389">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="23242-390">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-390">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-391">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-391">SDK version</span></span> | <span data-ttu-id="23242-392">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-392">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-393">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-393">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-394">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-394">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="23242-395">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="23242-395">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-396">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-396">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-397">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-397">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="23242-398">nunit</span><span class="sxs-lookup"><span data-stu-id="23242-398">nunit</span></span>

- <span data-ttu-id="23242-399">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-399">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="23242-400">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-400">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="23242-401">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-401">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-402">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-402">SDK version</span></span> | <span data-ttu-id="23242-403">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-403">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-404">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-404">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-405">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-405">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="23242-406">2.2</span><span class="sxs-lookup"><span data-stu-id="23242-406">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="23242-407">2.1</span><span class="sxs-lookup"><span data-stu-id="23242-407">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="23242-408">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="23242-408">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-409">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-409">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-410">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-410">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="23242-411">страница</span><span class="sxs-lookup"><span data-stu-id="23242-411">page</span></span>

- <span data-ttu-id="23242-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="23242-413">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="23242-413">Namespace for the generated code.</span></span> <span data-ttu-id="23242-414">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="23242-414">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="23242-415">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="23242-415">Creates the page without a PageModel.</span></span>

<span data-ttu-id="23242-416">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-416">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="23242-417">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="23242-417">viewimports, proto</span></span>

- <span data-ttu-id="23242-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="23242-419">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="23242-419">Namespace for the generated code.</span></span> <span data-ttu-id="23242-420">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="23242-420">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="23242-421">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-421">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="23242-422">blazorserver</span><span class="sxs-lookup"><span data-stu-id="23242-422">blazorserver</span></span>

- <span data-ttu-id="23242-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="23242-424">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-424">The type of authentication to use.</span></span> <span data-ttu-id="23242-425">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="23242-425">The possible values are:</span></span>

  - <span data-ttu-id="23242-426">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="23242-426">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="23242-427">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-427">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="23242-428">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="23242-428">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="23242-429">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="23242-429">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="23242-430">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="23242-430">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="23242-431">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="23242-431">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="23242-432">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-432">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="23242-433">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-433">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-434">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="23242-434">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="23242-435">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-435">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="23242-436">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-436">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="23242-437">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-437">The reset password policy ID for this project.</span></span> <span data-ttu-id="23242-438">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-438">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="23242-439">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-439">The edit profile policy ID for this project.</span></span> <span data-ttu-id="23242-440">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-440">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="23242-441">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-441">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="23242-442">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-442">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="23242-443">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="23242-443">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="23242-444">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-444">The Client ID for this project.</span></span> <span data-ttu-id="23242-445">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-445">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="23242-446">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="23242-446">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="23242-447">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="23242-447">The domain for the directory tenant.</span></span> <span data-ttu-id="23242-448">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-448">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-449">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="23242-449">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="23242-450">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-450">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="23242-451">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-451">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="23242-452">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="23242-452">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="23242-453">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="23242-453">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="23242-454">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-454">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-455">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="23242-455">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="23242-456">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="23242-456">Allows this application read-access to the directory.</span></span> <span data-ttu-id="23242-457">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-457">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="23242-458">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-458">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="23242-459">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23242-459">Turns off HTTPS.</span></span> <span data-ttu-id="23242-460">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="23242-460">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="23242-461">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="23242-461">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="23242-462">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-462">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-463">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-463">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-464">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-464">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="23242-465">web</span><span class="sxs-lookup"><span data-stu-id="23242-465">web</span></span>

- <span data-ttu-id="23242-466">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-466">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="23242-467">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-467">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="23242-468">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-469">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="23242-469">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="23242-470">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-470">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-471">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-471">SDK version</span></span> | <span data-ttu-id="23242-472">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-472">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-473">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-473">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-474">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-474">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="23242-475">2.1</span><span class="sxs-lookup"><span data-stu-id="23242-475">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="23242-476">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="23242-477">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23242-477">Turns off HTTPS.</span></span>

<span data-ttu-id="23242-478">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-478">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="23242-479">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="23242-479">mvc, webapp</span></span>

- <span data-ttu-id="23242-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="23242-481">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-481">The type of authentication to use.</span></span> <span data-ttu-id="23242-482">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="23242-482">The possible values are:</span></span>

  - <span data-ttu-id="23242-483">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="23242-483">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="23242-484">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-484">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="23242-485">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="23242-485">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="23242-486">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="23242-486">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="23242-487">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="23242-487">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="23242-488">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="23242-488">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="23242-489">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-489">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="23242-490">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-490">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-491">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="23242-491">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="23242-492">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-492">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="23242-493">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-493">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="23242-494">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-494">The reset password policy ID for this project.</span></span> <span data-ttu-id="23242-495">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-495">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="23242-496">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-496">The edit profile policy ID for this project.</span></span> <span data-ttu-id="23242-497">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-497">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="23242-498">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-498">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="23242-499">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-499">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="23242-500">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="23242-500">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="23242-501">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-501">The Client ID for this project.</span></span> <span data-ttu-id="23242-502">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-502">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="23242-503">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="23242-503">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="23242-504">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="23242-504">The domain for the directory tenant.</span></span> <span data-ttu-id="23242-505">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-506">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="23242-506">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="23242-507">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-507">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="23242-508">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-508">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="23242-509">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="23242-509">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="23242-510">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="23242-510">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="23242-511">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-511">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-512">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="23242-512">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="23242-513">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="23242-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="23242-514">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-514">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="23242-515">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="23242-516">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23242-516">Turns off HTTPS.</span></span> <span data-ttu-id="23242-517">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="23242-517">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="23242-518">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="23242-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="23242-519">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="23242-520">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-521">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-521">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="23242-522">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-523">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-523">SDK version</span></span> | <span data-ttu-id="23242-524">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-525">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-526">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-526">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="23242-527">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-527">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="23242-528">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="23242-528">Includes BrowserLink in the project.</span></span> <span data-ttu-id="23242-529">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="23242-529">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="23242-530">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="23242-530">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="23242-531">Параметр доступен начиная с пакета SDK для .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="23242-531">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="23242-532">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-532">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="23242-533">angular, react</span><span class="sxs-lookup"><span data-stu-id="23242-533">angular, react</span></span>

- <span data-ttu-id="23242-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="23242-535">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-535">The type of authentication to use.</span></span> <span data-ttu-id="23242-536">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-536">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="23242-537">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="23242-537">The possible values are:</span></span>

  - <span data-ttu-id="23242-538">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="23242-538">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="23242-539">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-539">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="23242-540">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-540">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="23242-541">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="23242-542">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23242-542">Turns off HTTPS.</span></span> <span data-ttu-id="23242-543">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="23242-543">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="23242-544">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="23242-544">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="23242-545">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-545">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-546">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-546">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="23242-547">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-547">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-548">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="23242-548">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="23242-549">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-549">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-550">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-550">SDK version</span></span> | <span data-ttu-id="23242-551">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-551">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-552">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-552">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-553">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-553">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="23242-554">2.1</span><span class="sxs-lookup"><span data-stu-id="23242-554">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="23242-555">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-555">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="23242-556">reactredux</span><span class="sxs-lookup"><span data-stu-id="23242-556">reactredux</span></span>

- <span data-ttu-id="23242-557">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-557">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="23242-558">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-558">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="23242-559">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-559">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-560">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="23242-560">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="23242-561">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-561">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-562">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-562">SDK version</span></span> | <span data-ttu-id="23242-563">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-563">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-564">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-564">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-565">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-565">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="23242-566">2.1</span><span class="sxs-lookup"><span data-stu-id="23242-566">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="23242-567">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-567">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="23242-568">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23242-568">Turns off HTTPS.</span></span>

<span data-ttu-id="23242-569">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-569">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="23242-570">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="23242-570">razorclasslib</span></span>

- <span data-ttu-id="23242-571">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-571">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="23242-572">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-572">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="23242-573">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="23242-573">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="23242-574">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="23242-574">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="23242-575">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-575">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="23242-576">webapi</span><span class="sxs-lookup"><span data-stu-id="23242-576">webapi</span></span>

- <span data-ttu-id="23242-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="23242-578">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-578">The type of authentication to use.</span></span> <span data-ttu-id="23242-579">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="23242-579">The possible values are:</span></span>

  - <span data-ttu-id="23242-580">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="23242-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="23242-581">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="23242-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="23242-582">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="23242-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="23242-583">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="23242-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="23242-584">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="23242-585">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="23242-586">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="23242-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="23242-587">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="23242-588">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="23242-589">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="23242-590">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="23242-591">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="23242-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="23242-592">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="23242-592">The Client ID for this project.</span></span> <span data-ttu-id="23242-593">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="23242-594">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="23242-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="23242-595">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="23242-595">The domain for the directory tenant.</span></span> <span data-ttu-id="23242-596">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="23242-597">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="23242-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="23242-598">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="23242-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="23242-599">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="23242-600">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="23242-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="23242-601">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="23242-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="23242-602">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="23242-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="23242-603">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="23242-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="23242-604">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23242-604">Turns off HTTPS.</span></span> <span data-ttu-id="23242-605">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="23242-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="23242-606">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="23242-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="23242-607">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="23242-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="23242-608">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="23242-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="23242-609">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="23242-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="23242-610">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="23242-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="23242-611">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="23242-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="23242-612">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="23242-612">SDK version</span></span> | <span data-ttu-id="23242-613">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="23242-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="23242-614">3.1</span><span class="sxs-lookup"><span data-stu-id="23242-614">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="23242-615">3.0</span><span class="sxs-lookup"><span data-stu-id="23242-615">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="23242-616">2.1</span><span class="sxs-lookup"><span data-stu-id="23242-616">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="23242-617">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="23242-617">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="23242-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="23242-618">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="23242-619">globaljson</span><span class="sxs-lookup"><span data-stu-id="23242-619">globaljson</span></span>

- <span data-ttu-id="23242-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="23242-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="23242-621">Задает версию пакета SDK для .NET Core, используемую в файле *global.json* .</span><span class="sxs-lookup"><span data-stu-id="23242-621">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="23242-622">Примеры</span><span class="sxs-lookup"><span data-stu-id="23242-622">Examples</span></span>

- <span data-ttu-id="23242-623">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="23242-623">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="23242-624">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="23242-624">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="23242-625">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="23242-625">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="23242-626">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="23242-626">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="23242-627">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="23242-627">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="23242-628">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="23242-628">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="23242-629">Список всех шаблонов, соответствующих подстроке *we* .</span><span class="sxs-lookup"><span data-stu-id="23242-629">List all templates matching the *we* substring.</span></span> <span data-ttu-id="23242-630">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="23242-630">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="23242-631">Попытайтесь вызвать шаблон, соответствующий *ng* .</span><span class="sxs-lookup"><span data-stu-id="23242-631">Attempt to invoke the template matching *ng* .</span></span> <span data-ttu-id="23242-632">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="23242-632">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="23242-633">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="23242-633">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="23242-634">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="23242-634">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="23242-635">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="23242-635">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="23242-636">См. также</span><span class="sxs-lookup"><span data-stu-id="23242-636">See also</span></span>

- [<span data-ttu-id="23242-637">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="23242-637">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="23242-638">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="23242-638">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="23242-639">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="23242-639">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="23242-640">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="23242-640">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
