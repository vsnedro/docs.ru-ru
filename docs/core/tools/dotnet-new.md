---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442245"
---
# <a name="dotnet-new"></a><span data-ttu-id="e900c-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e900c-103">dotnet new</span></span>

<span data-ttu-id="e900c-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e900c-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e900c-105">name</span><span class="sxs-lookup"><span data-stu-id="e900c-105">Name</span></span>

<span data-ttu-id="e900c-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e900c-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e900c-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="e900c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e900c-108">Description</span></span>

<span data-ttu-id="e900c-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="e900c-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="e900c-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="e900c-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="e900c-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e900c-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="e900c-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="e900c-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e900c-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="e900c-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e900c-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e900c-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="e900c-116">Вы можете запустить `dotnet new --list` или `dotnet new -l`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e900c-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="e900c-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="e900c-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="e900c-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="e900c-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="e900c-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="e900c-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="e900c-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="e900c-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="e900c-122">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e900c-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="e900c-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="e900c-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="e900c-124">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="e900c-125">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="e900c-125">Templates</span></span>                                    | <span data-ttu-id="e900c-126">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="e900c-126">Short name</span></span>                      | <span data-ttu-id="e900c-127">Язык</span><span class="sxs-lookup"><span data-stu-id="e900c-127">Language</span></span>     | <span data-ttu-id="e900c-128">Tags</span><span class="sxs-lookup"><span data-stu-id="e900c-128">Tags</span></span>                                  | <span data-ttu-id="e900c-129">Введенный</span><span class="sxs-lookup"><span data-stu-id="e900c-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="e900c-130">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e900c-130">Console Application</span></span>                          | [<span data-ttu-id="e900c-131">Консоль</span><span class="sxs-lookup"><span data-stu-id="e900c-131">console</span></span>](#console)             | <span data-ttu-id="e900c-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e900c-132">[C#], F#, VB</span></span> | <span data-ttu-id="e900c-133">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="e900c-133">Common/Console</span></span>                        | <span data-ttu-id="e900c-134">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-134">1.0</span></span>        |
| <span data-ttu-id="e900c-135">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="e900c-135">Class library</span></span>                                | [<span data-ttu-id="e900c-136">classlib</span><span class="sxs-lookup"><span data-stu-id="e900c-136">classlib</span></span>](#classlib)           | <span data-ttu-id="e900c-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e900c-137">[C#], F#, VB</span></span> | <span data-ttu-id="e900c-138">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="e900c-138">Common/Library</span></span>                        | <span data-ttu-id="e900c-139">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-139">1.0</span></span>        |
| <span data-ttu-id="e900c-140">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-140">WPF Application</span></span>                              | [<span data-ttu-id="e900c-141">wpf</span><span class="sxs-lookup"><span data-stu-id="e900c-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="e900c-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-142">[C#]</span></span>         | <span data-ttu-id="e900c-143">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-143">Common/WPF</span></span>                            | <span data-ttu-id="e900c-144">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-144">3.0</span></span>        |
| <span data-ttu-id="e900c-145">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-145">WPF Class library</span></span>                            | [<span data-ttu-id="e900c-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="e900c-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="e900c-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-147">[C#]</span></span>         | <span data-ttu-id="e900c-148">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-148">Common/WPF</span></span>                            | <span data-ttu-id="e900c-149">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-149">3.0</span></span>        |
| <span data-ttu-id="e900c-150">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="e900c-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="e900c-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="e900c-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-152">[C#]</span></span>         | <span data-ttu-id="e900c-153">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-153">Common/WPF</span></span>                            | <span data-ttu-id="e900c-154">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-154">3.0</span></span>        |
| <span data-ttu-id="e900c-155">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="e900c-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e900c-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="e900c-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-157">[C#]</span></span>         | <span data-ttu-id="e900c-158">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e900c-158">Common/WPF</span></span>                            | <span data-ttu-id="e900c-159">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-159">3.0</span></span>        |
| <span data-ttu-id="e900c-160">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e900c-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="e900c-161">winforms</span><span class="sxs-lookup"><span data-stu-id="e900c-161">winforms</span></span>](#winforms)           | <span data-ttu-id="e900c-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-162">[C#]</span></span>         | <span data-ttu-id="e900c-163">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e900c-163">Common/WinForms</span></span>                       | <span data-ttu-id="e900c-164">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-164">3.0</span></span>        |
| <span data-ttu-id="e900c-165">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e900c-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="e900c-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="e900c-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="e900c-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-167">[C#]</span></span>         | <span data-ttu-id="e900c-168">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e900c-168">Common/WinForms</span></span>                       | <span data-ttu-id="e900c-169">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-169">3.0</span></span>        |
| <span data-ttu-id="e900c-170">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="e900c-170">Worker Service</span></span>                               | [<span data-ttu-id="e900c-171">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="e900c-171">worker</span></span>](#web-others)           | <span data-ttu-id="e900c-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-172">[C#]</span></span>         | <span data-ttu-id="e900c-173">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="e900c-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="e900c-174">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-174">3.0</span></span>        |
| <span data-ttu-id="e900c-175">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="e900c-175">Unit Test Project</span></span>                            | [<span data-ttu-id="e900c-176">mstest</span><span class="sxs-lookup"><span data-stu-id="e900c-176">mstest</span></span>](#test)                 | <span data-ttu-id="e900c-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e900c-177">[C#], F#, VB</span></span> | <span data-ttu-id="e900c-178">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="e900c-178">Test/MSTest</span></span>                           | <span data-ttu-id="e900c-179">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-179">1.0</span></span>        |
| <span data-ttu-id="e900c-180">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e900c-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="e900c-181">nunit</span><span class="sxs-lookup"><span data-stu-id="e900c-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="e900c-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e900c-182">[C#], F#, VB</span></span> | <span data-ttu-id="e900c-183">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="e900c-183">Test/NUnit</span></span>                            | <span data-ttu-id="e900c-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="e900c-184">2.1.400</span></span>    |
| <span data-ttu-id="e900c-185">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e900c-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="e900c-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e900c-186">[C#], F#, VB</span></span> | <span data-ttu-id="e900c-187">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="e900c-187">Test/NUnit</span></span>                            | <span data-ttu-id="e900c-188">2.2</span><span class="sxs-lookup"><span data-stu-id="e900c-188">2.2</span></span>        |
| <span data-ttu-id="e900c-189">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="e900c-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="e900c-190">xunit</span><span class="sxs-lookup"><span data-stu-id="e900c-190">xunit</span></span>](#test)                  | <span data-ttu-id="e900c-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e900c-191">[C#], F#, VB</span></span> | <span data-ttu-id="e900c-192">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="e900c-192">Test/xUnit</span></span>                            | <span data-ttu-id="e900c-193">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-193">1.0</span></span>        |
| <span data-ttu-id="e900c-194">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="e900c-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="e900c-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-195">[C#]</span></span>         | <span data-ttu-id="e900c-196">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e900c-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="e900c-197">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-197">3.0</span></span>        |
| <span data-ttu-id="e900c-198">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="e900c-198">Razor Page</span></span>                                   | [<span data-ttu-id="e900c-199">page</span><span class="sxs-lookup"><span data-stu-id="e900c-199">page</span></span>](#page)                   | <span data-ttu-id="e900c-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-200">[C#]</span></span>         | <span data-ttu-id="e900c-201">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e900c-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="e900c-202">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-202">2.0</span></span>        |
| <span data-ttu-id="e900c-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e900c-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="e900c-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="e900c-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="e900c-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-205">[C#]</span></span>         | <span data-ttu-id="e900c-206">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e900c-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="e900c-207">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-207">2.0</span></span>        |
| <span data-ttu-id="e900c-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e900c-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="e900c-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-209">[C#]</span></span>         | <span data-ttu-id="e900c-210">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e900c-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="e900c-211">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-211">2.0</span></span>        |
| <span data-ttu-id="e900c-212">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="e900c-212">Blazor Server App</span></span>                            | [<span data-ttu-id="e900c-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e900c-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="e900c-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-214">[C#]</span></span>         | <span data-ttu-id="e900c-215">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="e900c-215">Web/Blazor</span></span>                            | <span data-ttu-id="e900c-216">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-216">3.0</span></span>        |
| <span data-ttu-id="e900c-217">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e900c-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="e900c-218">web</span><span class="sxs-lookup"><span data-stu-id="e900c-218">web</span></span>](#web)                     | <span data-ttu-id="e900c-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e900c-219">[C#], F#</span></span>     | <span data-ttu-id="e900c-220">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="e900c-220">Web/Empty</span></span>                             | <span data-ttu-id="e900c-221">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-221">1.0</span></span>        |
| <span data-ttu-id="e900c-222">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e900c-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="e900c-223">mvc</span><span class="sxs-lookup"><span data-stu-id="e900c-223">mvc</span></span>](#web-options)             | <span data-ttu-id="e900c-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e900c-224">[C#], F#</span></span>     | <span data-ttu-id="e900c-225">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="e900c-225">Web/MVC</span></span>                               | <span data-ttu-id="e900c-226">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-226">1.0</span></span>        |
| <span data-ttu-id="e900c-227">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e900c-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="e900c-228">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="e900c-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="e900c-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-229">[C#]</span></span>         | <span data-ttu-id="e900c-230">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="e900c-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="e900c-231">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="e900c-232">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="e900c-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="e900c-233">angular</span><span class="sxs-lookup"><span data-stu-id="e900c-233">angular</span></span>](#spa)                 | <span data-ttu-id="e900c-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-234">[C#]</span></span>         | <span data-ttu-id="e900c-235">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e900c-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e900c-236">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-236">2.0</span></span>        |
| <span data-ttu-id="e900c-237">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="e900c-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="e900c-238">react</span><span class="sxs-lookup"><span data-stu-id="e900c-238">react</span></span>](#spa)                   | <span data-ttu-id="e900c-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-239">[C#]</span></span>         | <span data-ttu-id="e900c-240">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e900c-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e900c-241">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-241">2.0</span></span>        |
| <span data-ttu-id="e900c-242">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="e900c-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="e900c-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="e900c-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="e900c-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-244">[C#]</span></span>         | <span data-ttu-id="e900c-245">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e900c-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e900c-246">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-246">2.0</span></span>        |
| <span data-ttu-id="e900c-247">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e900c-247">Razor Class Library</span></span>                          | [<span data-ttu-id="e900c-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e900c-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="e900c-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-249">[C#]</span></span>         | <span data-ttu-id="e900c-250">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e900c-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="e900c-251">2.1</span><span class="sxs-lookup"><span data-stu-id="e900c-251">2.1</span></span>        |
| <span data-ttu-id="e900c-252">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e900c-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="e900c-253">webapi</span><span class="sxs-lookup"><span data-stu-id="e900c-253">webapi</span></span>](#webapi)               | <span data-ttu-id="e900c-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e900c-254">[C#], F#</span></span>     | <span data-ttu-id="e900c-255">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="e900c-255">Web/WebAPI</span></span>                            | <span data-ttu-id="e900c-256">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-256">1.0</span></span>        |
| <span data-ttu-id="e900c-257">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e900c-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="e900c-258">grpc</span><span class="sxs-lookup"><span data-stu-id="e900c-258">grpc</span></span>](#web-others)             | <span data-ttu-id="e900c-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="e900c-259">[C#]</span></span>         | <span data-ttu-id="e900c-260">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="e900c-260">Web/gRPC</span></span>                              | <span data-ttu-id="e900c-261">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-261">3.0</span></span>        |
| <span data-ttu-id="e900c-262">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="e900c-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="e900c-263">Config</span><span class="sxs-lookup"><span data-stu-id="e900c-263">Config</span></span>                                | <span data-ttu-id="e900c-264">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-264">3.0</span></span>        |
| <span data-ttu-id="e900c-265">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="e900c-265">global.json file</span></span>                             | [<span data-ttu-id="e900c-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="e900c-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="e900c-267">Config</span><span class="sxs-lookup"><span data-stu-id="e900c-267">Config</span></span>                                | <span data-ttu-id="e900c-268">2.0</span><span class="sxs-lookup"><span data-stu-id="e900c-268">2.0</span></span>        |
| <span data-ttu-id="e900c-269">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="e900c-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="e900c-270">Config</span><span class="sxs-lookup"><span data-stu-id="e900c-270">Config</span></span>                                | <span data-ttu-id="e900c-271">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-271">1.0</span></span>        |
| <span data-ttu-id="e900c-272">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="e900c-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="e900c-273">Config</span><span class="sxs-lookup"><span data-stu-id="e900c-273">Config</span></span>                                | <span data-ttu-id="e900c-274">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-274">3.0</span></span>        |
| <span data-ttu-id="e900c-275">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="e900c-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="e900c-276">Config</span><span class="sxs-lookup"><span data-stu-id="e900c-276">Config</span></span>                                | <span data-ttu-id="e900c-277">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-277">1.0</span></span>        |
| <span data-ttu-id="e900c-278">Файл решения</span><span class="sxs-lookup"><span data-stu-id="e900c-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="e900c-279">Решение</span><span class="sxs-lookup"><span data-stu-id="e900c-279">Solution</span></span>                              | <span data-ttu-id="e900c-280">1.0</span><span class="sxs-lookup"><span data-stu-id="e900c-280">1.0</span></span>        |
| <span data-ttu-id="e900c-281">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="e900c-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="e900c-282">proto</span><span class="sxs-lookup"><span data-stu-id="e900c-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="e900c-283">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="e900c-283">Web/gRPC</span></span>                              | <span data-ttu-id="e900c-284">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="e900c-285">Параметры</span><span class="sxs-lookup"><span data-stu-id="e900c-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="e900c-286">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="e900c-287">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e900c-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="e900c-288">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="e900c-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e900c-289">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="e900c-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e900c-290">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="e900c-290">Prints out help for the command.</span></span> <span data-ttu-id="e900c-291">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="e900c-292">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e900c-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="e900c-293">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e900c-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e900c-294">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e900c-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e900c-295">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="e900c-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="e900c-296">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="e900c-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="e900c-297">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="e900c-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="e900c-298">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="e900c-299">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e900c-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="e900c-300">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e900c-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="e900c-301">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-301">The language of the template to create.</span></span> <span data-ttu-id="e900c-302">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e900c-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e900c-303">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e900c-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e900c-304">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="e900c-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e900c-305">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="e900c-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="e900c-306">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e900c-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="e900c-307">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e900c-307">The name for the created output.</span></span> <span data-ttu-id="e900c-308">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="e900c-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="e900c-309">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="e900c-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="e900c-310">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="e900c-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e900c-311">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e900c-311">Location to place the generated output.</span></span> <span data-ttu-id="e900c-312">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e900c-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="e900c-313">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="e900c-313">Filters templates based on available types.</span></span> <span data-ttu-id="e900c-314">Предопределенные значения: `project`, `item` и `other`.</span><span class="sxs-lookup"><span data-stu-id="e900c-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="e900c-315">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e900c-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e900c-316">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e900c-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="e900c-317">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e900c-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="e900c-318">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="e900c-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e900c-319">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="e900c-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e900c-320">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="e900c-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="e900c-321">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="e900c-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="e900c-322">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="e900c-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="e900c-323">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="e900c-324">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e900c-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="e900c-325">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="e900c-326">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="e900c-326">Template options</span></span>

<span data-ttu-id="e900c-327">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="e900c-327">Each project template may have additional options available.</span></span> <span data-ttu-id="e900c-328">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="e900c-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="e900c-329">console</span><span class="sxs-lookup"><span data-stu-id="e900c-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-330">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-331">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e900c-332">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-333">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-333">SDK version</span></span> | <span data-ttu-id="e900c-334">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-335">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-336">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e900c-337">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e900c-338">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e900c-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e900c-339">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="e900c-339">Not supported for F#.</span></span> <span data-ttu-id="e900c-340">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e900c-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e900c-341">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e900c-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-342">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="e900c-343">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e900c-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="e900c-344">classlib</span><span class="sxs-lookup"><span data-stu-id="e900c-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-345">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-346">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="e900c-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e900c-347">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e900c-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e900c-348">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e900c-349">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e900c-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e900c-350">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="e900c-350">Not supported for F#.</span></span> <span data-ttu-id="e900c-351">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e900c-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e900c-352">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e900c-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-353">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="e900c-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e900c-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-355">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-356">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e900c-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e900c-357">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e900c-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e900c-358">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e900c-359">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e900c-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e900c-360">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e900c-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-361">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="e900c-362">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="e900c-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e900c-363">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e900c-364">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e900c-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e900c-365">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e900c-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-366">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="e900c-367">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="e900c-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-368">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-369">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e900c-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e900c-370">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e900c-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-371">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-372">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="e900c-373">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="e900c-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-374">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-375">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e900c-376">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-377">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-377">SDK version</span></span> | <span data-ttu-id="e900c-378">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-379">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-380">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e900c-381">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-382">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="e900c-383">nunit</span><span class="sxs-lookup"><span data-stu-id="e900c-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-384">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e900c-385">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-386">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-386">SDK version</span></span> | <span data-ttu-id="e900c-387">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-388">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-389">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e900c-390">2.2</span><span class="sxs-lookup"><span data-stu-id="e900c-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="e900c-391">2.1</span><span class="sxs-lookup"><span data-stu-id="e900c-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e900c-392">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-393">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="e900c-394">страница</span><span class="sxs-lookup"><span data-stu-id="e900c-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e900c-395">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="e900c-395">Namespace for the generated code.</span></span> <span data-ttu-id="e900c-396">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e900c-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="e900c-397">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="e900c-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="e900c-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="e900c-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e900c-399">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="e900c-399">Namespace for the generated code.</span></span> <span data-ttu-id="e900c-400">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e900c-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="e900c-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e900c-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e900c-402">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-402">The type of authentication to use.</span></span> <span data-ttu-id="e900c-403">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e900c-403">The possible values are:</span></span>

  - <span data-ttu-id="e900c-404">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e900c-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e900c-405">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e900c-406">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e900c-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e900c-407">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e900c-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e900c-408">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e900c-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e900c-409">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e900c-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e900c-410">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e900c-411">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-412">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e900c-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e900c-413">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e900c-414">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e900c-415">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="e900c-416">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e900c-417">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e900c-418">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e900c-419">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e900c-420">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e900c-421">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e900c-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e900c-422">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-422">The Client ID for this project.</span></span> <span data-ttu-id="e900c-423">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e900c-424">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e900c-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e900c-425">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e900c-425">The domain for the directory tenant.</span></span> <span data-ttu-id="e900c-426">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-427">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e900c-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e900c-428">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e900c-429">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e900c-430">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e900c-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e900c-431">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e900c-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e900c-432">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-433">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e900c-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e900c-434">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e900c-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e900c-435">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-436">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e900c-437">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e900c-437">Turns off HTTPS.</span></span> <span data-ttu-id="e900c-438">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e900c-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e900c-439">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e900c-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e900c-440">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-441">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="e900c-442">web</span><span class="sxs-lookup"><span data-stu-id="e900c-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-443">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-444">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-445">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e900c-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e900c-446">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-447">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-447">SDK version</span></span> | <span data-ttu-id="e900c-448">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-449">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-450">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e900c-451">2.1</span><span class="sxs-lookup"><span data-stu-id="e900c-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e900c-452">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e900c-453">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e900c-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="e900c-454">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="e900c-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e900c-455">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-455">The type of authentication to use.</span></span> <span data-ttu-id="e900c-456">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e900c-456">The possible values are:</span></span>

  - <span data-ttu-id="e900c-457">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e900c-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e900c-458">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e900c-459">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e900c-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e900c-460">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e900c-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e900c-461">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e900c-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e900c-462">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e900c-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e900c-463">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e900c-464">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-465">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e900c-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e900c-466">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e900c-467">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e900c-468">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="e900c-469">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e900c-470">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e900c-471">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e900c-472">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e900c-473">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e900c-474">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e900c-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e900c-475">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-475">The Client ID for this project.</span></span> <span data-ttu-id="e900c-476">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e900c-477">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e900c-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e900c-478">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e900c-478">The domain for the directory tenant.</span></span> <span data-ttu-id="e900c-479">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-480">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e900c-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e900c-481">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e900c-482">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e900c-483">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e900c-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e900c-484">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e900c-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e900c-485">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-486">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e900c-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e900c-487">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e900c-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e900c-488">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-489">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e900c-490">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e900c-490">Turns off HTTPS.</span></span> <span data-ttu-id="e900c-491">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="e900c-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e900c-492">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e900c-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e900c-493">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-494">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-495">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e900c-496">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-497">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-497">SDK version</span></span> | <span data-ttu-id="e900c-498">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-499">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-500">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="e900c-501">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="e900c-502">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="e900c-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="e900c-503">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e900c-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="e900c-504">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="e900c-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="e900c-505">Параметр доступен начиная с пакета SDK для .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="e900c-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="e900c-506">angular, react</span><span class="sxs-lookup"><span data-stu-id="e900c-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e900c-507">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-507">The type of authentication to use.</span></span> <span data-ttu-id="e900c-508">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="e900c-509">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e900c-509">The possible values are:</span></span>

  - <span data-ttu-id="e900c-510">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e900c-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e900c-511">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-512">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-513">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e900c-514">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e900c-514">Turns off HTTPS.</span></span> <span data-ttu-id="e900c-515">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="e900c-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e900c-516">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e900c-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e900c-517">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-518">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-519">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-520">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e900c-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e900c-521">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-522">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-522">SDK version</span></span> | <span data-ttu-id="e900c-523">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-524">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-525">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e900c-526">2.1</span><span class="sxs-lookup"><span data-stu-id="e900c-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="e900c-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="e900c-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-528">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-529">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-530">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e900c-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e900c-531">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-532">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-532">SDK version</span></span> | <span data-ttu-id="e900c-533">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-534">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-535">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e900c-536">2.1</span><span class="sxs-lookup"><span data-stu-id="e900c-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="e900c-537">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e900c-538">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e900c-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="e900c-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e900c-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="e900c-540">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="e900c-541">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e900c-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="e900c-542">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e900c-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="e900c-543">webapi</span><span class="sxs-lookup"><span data-stu-id="e900c-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e900c-544">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-544">The type of authentication to use.</span></span> <span data-ttu-id="e900c-545">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e900c-545">The possible values are:</span></span>

  - <span data-ttu-id="e900c-546">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e900c-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e900c-547">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e900c-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e900c-548">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e900c-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e900c-549">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e900c-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e900c-550">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e900c-551">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e900c-552">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e900c-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e900c-553">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e900c-554">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e900c-555">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e900c-556">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e900c-557">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e900c-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e900c-558">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e900c-558">The Client ID for this project.</span></span> <span data-ttu-id="e900c-559">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e900c-560">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e900c-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e900c-561">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e900c-561">The domain for the directory tenant.</span></span> <span data-ttu-id="e900c-562">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e900c-563">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e900c-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e900c-564">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e900c-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e900c-565">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e900c-566">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e900c-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e900c-567">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e900c-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e900c-568">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e900c-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e900c-569">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e900c-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e900c-570">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e900c-570">Turns off HTTPS.</span></span> <span data-ttu-id="e900c-571">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e900c-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e900c-572">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e900c-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e900c-573">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e900c-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e900c-574">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e900c-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e900c-575">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e900c-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e900c-576">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e900c-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e900c-577">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e900c-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e900c-578">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e900c-578">SDK version</span></span> | <span data-ttu-id="e900c-579">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e900c-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e900c-580">3.1</span><span class="sxs-lookup"><span data-stu-id="e900c-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e900c-581">3.0</span><span class="sxs-lookup"><span data-stu-id="e900c-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e900c-582">2.1</span><span class="sxs-lookup"><span data-stu-id="e900c-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e900c-583">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e900c-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="e900c-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="e900c-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="e900c-585">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e900c-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="e900c-586">Примеры</span><span class="sxs-lookup"><span data-stu-id="e900c-586">Examples</span></span>

- <span data-ttu-id="e900c-587">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="e900c-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="e900c-588">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="e900c-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="e900c-589">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="e900c-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="e900c-590">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="e900c-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="e900c-591">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="e900c-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="e900c-592">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="e900c-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="e900c-593">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="e900c-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="e900c-594">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="e900c-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="e900c-595">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="e900c-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="e900c-596">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="e900c-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="e900c-597">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="e900c-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="e900c-598">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="e900c-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="e900c-599">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="e900c-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="e900c-600">См. также</span><span class="sxs-lookup"><span data-stu-id="e900c-600">See also</span></span>

- [<span data-ttu-id="e900c-601">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e900c-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="e900c-602">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="e900c-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="e900c-603">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="e900c-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="e900c-604">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e900c-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
