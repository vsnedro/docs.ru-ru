---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 04/10/2020
ms.openlocfilehash: 9a68baafa7ac3e6ad2fdc8f1c6e8621d6e15f1ff
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506861"
---
# <a name="dotnet-new"></a><span data-ttu-id="d2242-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2242-103">dotnet new</span></span>

<span data-ttu-id="d2242-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d2242-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d2242-105">name</span><span class="sxs-lookup"><span data-stu-id="d2242-105">Name</span></span>

<span data-ttu-id="d2242-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2242-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d2242-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="d2242-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d2242-108">Description</span></span>

<span data-ttu-id="d2242-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="d2242-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="d2242-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="d2242-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="d2242-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d2242-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="d2242-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="d2242-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d2242-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="d2242-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d2242-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="d2242-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="d2242-116">Вы можете запустить `dotnet new --list` или `dotnet new -l`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d2242-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="d2242-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="d2242-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="d2242-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="d2242-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="d2242-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="d2242-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="d2242-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="d2242-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="d2242-122">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d2242-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="d2242-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="d2242-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="d2242-124">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="d2242-125">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="d2242-125">Templates</span></span>                                    | <span data-ttu-id="d2242-126">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="d2242-126">Short name</span></span>                      | <span data-ttu-id="d2242-127">Язык</span><span class="sxs-lookup"><span data-stu-id="d2242-127">Language</span></span>     | <span data-ttu-id="d2242-128">Tags</span><span class="sxs-lookup"><span data-stu-id="d2242-128">Tags</span></span>                                  | <span data-ttu-id="d2242-129">Введенный</span><span class="sxs-lookup"><span data-stu-id="d2242-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="d2242-130">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="d2242-130">Console Application</span></span>                          | [<span data-ttu-id="d2242-131">Консоль</span><span class="sxs-lookup"><span data-stu-id="d2242-131">console</span></span>](#console)             | <span data-ttu-id="d2242-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2242-132">[C#], F#, VB</span></span> | <span data-ttu-id="d2242-133">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="d2242-133">Common/Console</span></span>                        | <span data-ttu-id="d2242-134">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-134">1.0</span></span>        |
| <span data-ttu-id="d2242-135">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="d2242-135">Class library</span></span>                                | [<span data-ttu-id="d2242-136">classlib</span><span class="sxs-lookup"><span data-stu-id="d2242-136">classlib</span></span>](#classlib)           | <span data-ttu-id="d2242-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2242-137">[C#], F#, VB</span></span> | <span data-ttu-id="d2242-138">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="d2242-138">Common/Library</span></span>                        | <span data-ttu-id="d2242-139">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-139">1.0</span></span>        |
| <span data-ttu-id="d2242-140">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-140">WPF Application</span></span>                              | [<span data-ttu-id="d2242-141">wpf</span><span class="sxs-lookup"><span data-stu-id="d2242-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="d2242-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-142">[C#]</span></span>         | <span data-ttu-id="d2242-143">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-143">Common/WPF</span></span>                            | <span data-ttu-id="d2242-144">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-144">3.0</span></span>        |
| <span data-ttu-id="d2242-145">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-145">WPF Class library</span></span>                            | [<span data-ttu-id="d2242-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="d2242-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="d2242-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-147">[C#]</span></span>         | <span data-ttu-id="d2242-148">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-148">Common/WPF</span></span>                            | <span data-ttu-id="d2242-149">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-149">3.0</span></span>        |
| <span data-ttu-id="d2242-150">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="d2242-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="d2242-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="d2242-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-152">[C#]</span></span>         | <span data-ttu-id="d2242-153">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-153">Common/WPF</span></span>                            | <span data-ttu-id="d2242-154">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-154">3.0</span></span>        |
| <span data-ttu-id="d2242-155">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="d2242-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="d2242-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="d2242-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-157">[C#]</span></span>         | <span data-ttu-id="d2242-158">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="d2242-158">Common/WPF</span></span>                            | <span data-ttu-id="d2242-159">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-159">3.0</span></span>        |
| <span data-ttu-id="d2242-160">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="d2242-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="d2242-161">winforms</span><span class="sxs-lookup"><span data-stu-id="d2242-161">winforms</span></span>](#winforms)           | <span data-ttu-id="d2242-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-162">[C#]</span></span>         | <span data-ttu-id="d2242-163">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="d2242-163">Common/WinForms</span></span>                       | <span data-ttu-id="d2242-164">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-164">3.0</span></span>        |
| <span data-ttu-id="d2242-165">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="d2242-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="d2242-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="d2242-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="d2242-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-167">[C#]</span></span>         | <span data-ttu-id="d2242-168">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="d2242-168">Common/WinForms</span></span>                       | <span data-ttu-id="d2242-169">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-169">3.0</span></span>        |
| <span data-ttu-id="d2242-170">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="d2242-170">Worker Service</span></span>                               | [<span data-ttu-id="d2242-171">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="d2242-171">worker</span></span>](#web-others)           | <span data-ttu-id="d2242-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-172">[C#]</span></span>         | <span data-ttu-id="d2242-173">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="d2242-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="d2242-174">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-174">3.0</span></span>        |
| <span data-ttu-id="d2242-175">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="d2242-175">Unit Test Project</span></span>                            | [<span data-ttu-id="d2242-176">mstest</span><span class="sxs-lookup"><span data-stu-id="d2242-176">mstest</span></span>](#test)                 | <span data-ttu-id="d2242-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2242-177">[C#], F#, VB</span></span> | <span data-ttu-id="d2242-178">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="d2242-178">Test/MSTest</span></span>                           | <span data-ttu-id="d2242-179">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-179">1.0</span></span>        |
| <span data-ttu-id="d2242-180">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="d2242-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="d2242-181">nunit</span><span class="sxs-lookup"><span data-stu-id="d2242-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="d2242-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2242-182">[C#], F#, VB</span></span> | <span data-ttu-id="d2242-183">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="d2242-183">Test/NUnit</span></span>                            | <span data-ttu-id="d2242-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="d2242-184">2.1.400</span></span>    |
| <span data-ttu-id="d2242-185">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="d2242-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="d2242-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2242-186">[C#], F#, VB</span></span> | <span data-ttu-id="d2242-187">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="d2242-187">Test/NUnit</span></span>                            | <span data-ttu-id="d2242-188">2.2</span><span class="sxs-lookup"><span data-stu-id="d2242-188">2.2</span></span>        |
| <span data-ttu-id="d2242-189">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="d2242-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="d2242-190">xunit</span><span class="sxs-lookup"><span data-stu-id="d2242-190">xunit</span></span>](#test)                  | <span data-ttu-id="d2242-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2242-191">[C#], F#, VB</span></span> | <span data-ttu-id="d2242-192">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="d2242-192">Test/xUnit</span></span>                            | <span data-ttu-id="d2242-193">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-193">1.0</span></span>        |
| <span data-ttu-id="d2242-194">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="d2242-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="d2242-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-195">[C#]</span></span>         | <span data-ttu-id="d2242-196">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2242-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="d2242-197">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-197">3.0</span></span>        |
| <span data-ttu-id="d2242-198">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="d2242-198">Razor Page</span></span>                                   | [<span data-ttu-id="d2242-199">page</span><span class="sxs-lookup"><span data-stu-id="d2242-199">page</span></span>](#page)                   | <span data-ttu-id="d2242-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-200">[C#]</span></span>         | <span data-ttu-id="d2242-201">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2242-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="d2242-202">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-202">2.0</span></span>        |
| <span data-ttu-id="d2242-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="d2242-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="d2242-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="d2242-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="d2242-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-205">[C#]</span></span>         | <span data-ttu-id="d2242-206">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2242-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="d2242-207">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-207">2.0</span></span>        |
| <span data-ttu-id="d2242-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d2242-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="d2242-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-209">[C#]</span></span>         | <span data-ttu-id="d2242-210">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2242-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="d2242-211">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-211">2.0</span></span>        |
| <span data-ttu-id="d2242-212">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="d2242-212">Blazor Server App</span></span>                            | [<span data-ttu-id="d2242-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="d2242-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="d2242-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-214">[C#]</span></span>         | <span data-ttu-id="d2242-215">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="d2242-215">Web/Blazor</span></span>                            | <span data-ttu-id="d2242-216">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-216">3.0</span></span>        |
| <span data-ttu-id="d2242-217">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2242-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="d2242-218">web</span><span class="sxs-lookup"><span data-stu-id="d2242-218">web</span></span>](#web)                     | <span data-ttu-id="d2242-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2242-219">[C#], F#</span></span>     | <span data-ttu-id="d2242-220">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="d2242-220">Web/Empty</span></span>                             | <span data-ttu-id="d2242-221">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-221">1.0</span></span>        |
| <span data-ttu-id="d2242-222">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d2242-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="d2242-223">mvc</span><span class="sxs-lookup"><span data-stu-id="d2242-223">mvc</span></span>](#web-options)             | <span data-ttu-id="d2242-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2242-224">[C#], F#</span></span>     | <span data-ttu-id="d2242-225">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="d2242-225">Web/MVC</span></span>                               | <span data-ttu-id="d2242-226">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-226">1.0</span></span>        |
| <span data-ttu-id="d2242-227">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2242-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="d2242-228">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="d2242-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="d2242-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-229">[C#]</span></span>         | <span data-ttu-id="d2242-230">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="d2242-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="d2242-231">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="d2242-232">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="d2242-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="d2242-233">angular</span><span class="sxs-lookup"><span data-stu-id="d2242-233">angular</span></span>](#spa)                 | <span data-ttu-id="d2242-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-234">[C#]</span></span>         | <span data-ttu-id="d2242-235">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="d2242-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="d2242-236">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-236">2.0</span></span>        |
| <span data-ttu-id="d2242-237">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="d2242-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="d2242-238">react</span><span class="sxs-lookup"><span data-stu-id="d2242-238">react</span></span>](#spa)                   | <span data-ttu-id="d2242-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-239">[C#]</span></span>         | <span data-ttu-id="d2242-240">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="d2242-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="d2242-241">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-241">2.0</span></span>        |
| <span data-ttu-id="d2242-242">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="d2242-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="d2242-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="d2242-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="d2242-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-244">[C#]</span></span>         | <span data-ttu-id="d2242-245">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="d2242-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="d2242-246">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-246">2.0</span></span>        |
| <span data-ttu-id="d2242-247">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="d2242-247">Razor Class Library</span></span>                          | [<span data-ttu-id="d2242-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="d2242-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="d2242-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-249">[C#]</span></span>         | <span data-ttu-id="d2242-250">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="d2242-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="d2242-251">2.1</span><span class="sxs-lookup"><span data-stu-id="d2242-251">2.1</span></span>        |
| <span data-ttu-id="d2242-252">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2242-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="d2242-253">webapi</span><span class="sxs-lookup"><span data-stu-id="d2242-253">webapi</span></span>](#webapi)               | <span data-ttu-id="d2242-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2242-254">[C#], F#</span></span>     | <span data-ttu-id="d2242-255">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="d2242-255">Web/WebAPI</span></span>                            | <span data-ttu-id="d2242-256">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-256">1.0</span></span>        |
| <span data-ttu-id="d2242-257">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="d2242-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="d2242-258">grpc</span><span class="sxs-lookup"><span data-stu-id="d2242-258">grpc</span></span>](#web-others)             | <span data-ttu-id="d2242-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2242-259">[C#]</span></span>         | <span data-ttu-id="d2242-260">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="d2242-260">Web/gRPC</span></span>                              | <span data-ttu-id="d2242-261">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-261">3.0</span></span>        |
| <span data-ttu-id="d2242-262">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="d2242-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="d2242-263">Config</span><span class="sxs-lookup"><span data-stu-id="d2242-263">Config</span></span>                                | <span data-ttu-id="d2242-264">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-264">3.0</span></span>        |
| <span data-ttu-id="d2242-265">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="d2242-265">global.json file</span></span>                             | [<span data-ttu-id="d2242-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="d2242-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="d2242-267">Config</span><span class="sxs-lookup"><span data-stu-id="d2242-267">Config</span></span>                                | <span data-ttu-id="d2242-268">2.0</span><span class="sxs-lookup"><span data-stu-id="d2242-268">2.0</span></span>        |
| <span data-ttu-id="d2242-269">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="d2242-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="d2242-270">Config</span><span class="sxs-lookup"><span data-stu-id="d2242-270">Config</span></span>                                | <span data-ttu-id="d2242-271">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-271">1.0</span></span>        |
| <span data-ttu-id="d2242-272">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="d2242-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="d2242-273">Config</span><span class="sxs-lookup"><span data-stu-id="d2242-273">Config</span></span>                                | <span data-ttu-id="d2242-274">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-274">3.0</span></span>        |
| <span data-ttu-id="d2242-275">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="d2242-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="d2242-276">Config</span><span class="sxs-lookup"><span data-stu-id="d2242-276">Config</span></span>                                | <span data-ttu-id="d2242-277">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-277">1.0</span></span>        |
| <span data-ttu-id="d2242-278">Файл решения</span><span class="sxs-lookup"><span data-stu-id="d2242-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="d2242-279">Решение</span><span class="sxs-lookup"><span data-stu-id="d2242-279">Solution</span></span>                              | <span data-ttu-id="d2242-280">1.0</span><span class="sxs-lookup"><span data-stu-id="d2242-280">1.0</span></span>        |
| <span data-ttu-id="d2242-281">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="d2242-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="d2242-282">proto</span><span class="sxs-lookup"><span data-stu-id="d2242-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="d2242-283">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="d2242-283">Web/gRPC</span></span>                              | <span data-ttu-id="d2242-284">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="d2242-285">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2242-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="d2242-286">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="d2242-287">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="d2242-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="d2242-288">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="d2242-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d2242-289">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="d2242-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d2242-290">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="d2242-290">Prints out help for the command.</span></span> <span data-ttu-id="d2242-291">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="d2242-292">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="d2242-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="d2242-293">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d2242-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d2242-294">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="d2242-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="d2242-295">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="d2242-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="d2242-296">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="d2242-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="d2242-297">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="d2242-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="d2242-298">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="d2242-299">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="d2242-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="d2242-300">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="d2242-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="d2242-301">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-301">The language of the template to create.</span></span> <span data-ttu-id="d2242-302">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="d2242-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d2242-303">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d2242-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d2242-304">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="d2242-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="d2242-305">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="d2242-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="d2242-306">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="d2242-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="d2242-307">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d2242-307">The name for the created output.</span></span> <span data-ttu-id="d2242-308">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="d2242-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="d2242-309">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="d2242-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="d2242-310">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="d2242-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="d2242-311">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d2242-311">Location to place the generated output.</span></span> <span data-ttu-id="d2242-312">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d2242-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="d2242-313">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="d2242-313">Filters templates based on available types.</span></span> <span data-ttu-id="d2242-314">Предопределенные значения: `project`, `item` и `other`.</span><span class="sxs-lookup"><span data-stu-id="d2242-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="d2242-315">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d2242-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d2242-316">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="d2242-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="d2242-317">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d2242-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="d2242-318">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="d2242-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d2242-319">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="d2242-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d2242-320">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="d2242-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="d2242-321">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="d2242-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="d2242-322">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="d2242-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="d2242-323">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="d2242-324">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d2242-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="d2242-325">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="d2242-326">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="d2242-326">Template options</span></span>

<span data-ttu-id="d2242-327">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="d2242-327">Each project template may have additional options available.</span></span> <span data-ttu-id="d2242-328">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="d2242-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="d2242-329">console</span><span class="sxs-lookup"><span data-stu-id="d2242-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-330">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-331">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="d2242-332">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-333">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-333">SDK version</span></span> | <span data-ttu-id="d2242-334">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-335">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-336">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d2242-337">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d2242-338">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="d2242-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="d2242-339">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="d2242-339">Not supported for F#.</span></span> <span data-ttu-id="d2242-340">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="d2242-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d2242-341">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="d2242-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-342">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="d2242-343">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="d2242-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="d2242-344">classlib</span><span class="sxs-lookup"><span data-stu-id="d2242-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-345">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-346">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="d2242-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d2242-347">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="d2242-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d2242-348">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d2242-349">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="d2242-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="d2242-350">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="d2242-350">Not supported for F#.</span></span> <span data-ttu-id="d2242-351">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="d2242-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d2242-352">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="d2242-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-353">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="d2242-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="d2242-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-355">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-356">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="d2242-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="d2242-357">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="d2242-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d2242-358">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d2242-359">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="d2242-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="d2242-360">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="d2242-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-361">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="d2242-362">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="d2242-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d2242-363">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d2242-364">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="d2242-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="d2242-365">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="d2242-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-366">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="d2242-367">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="d2242-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-368">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-369">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="d2242-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="d2242-370">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="d2242-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-371">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-372">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="d2242-373">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="d2242-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-374">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-375">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="d2242-376">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-377">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-377">SDK version</span></span> | <span data-ttu-id="d2242-378">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-379">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-380">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="d2242-381">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-382">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="d2242-383">nunit</span><span class="sxs-lookup"><span data-stu-id="d2242-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-384">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="d2242-385">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-386">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-386">SDK version</span></span> | <span data-ttu-id="d2242-387">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-388">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-389">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d2242-390">2.2</span><span class="sxs-lookup"><span data-stu-id="d2242-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="d2242-391">2.1</span><span class="sxs-lookup"><span data-stu-id="d2242-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="d2242-392">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-393">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="d2242-394">страница</span><span class="sxs-lookup"><span data-stu-id="d2242-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="d2242-395">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="d2242-395">Namespace for the generated code.</span></span> <span data-ttu-id="d2242-396">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d2242-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="d2242-397">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="d2242-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="d2242-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="d2242-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="d2242-399">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="d2242-399">Namespace for the generated code.</span></span> <span data-ttu-id="d2242-400">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d2242-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="d2242-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="d2242-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d2242-402">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-402">The type of authentication to use.</span></span> <span data-ttu-id="d2242-403">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d2242-403">The possible values are:</span></span>

  - <span data-ttu-id="d2242-404">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d2242-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d2242-405">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="d2242-406">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d2242-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="d2242-407">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="d2242-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="d2242-408">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="d2242-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="d2242-409">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d2242-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="d2242-410">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d2242-411">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-412">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d2242-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="d2242-413">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d2242-414">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="d2242-415">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="d2242-416">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="d2242-417">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="d2242-418">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="d2242-419">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d2242-420">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d2242-421">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d2242-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="d2242-422">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-422">The Client ID for this project.</span></span> <span data-ttu-id="d2242-423">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d2242-424">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d2242-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="d2242-425">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="d2242-425">The domain for the directory tenant.</span></span> <span data-ttu-id="d2242-426">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-427">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d2242-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="d2242-428">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d2242-429">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d2242-430">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d2242-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="d2242-431">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="d2242-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d2242-432">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-433">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="d2242-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="d2242-434">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="d2242-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="d2242-435">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-436">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="d2242-437">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d2242-437">Turns off HTTPS.</span></span> <span data-ttu-id="d2242-438">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="d2242-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d2242-439">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d2242-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d2242-440">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-441">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="d2242-442">web</span><span class="sxs-lookup"><span data-stu-id="d2242-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-443">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-444">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-445">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2242-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d2242-446">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-447">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-447">SDK version</span></span> | <span data-ttu-id="d2242-448">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-449">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-450">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d2242-451">2.1</span><span class="sxs-lookup"><span data-stu-id="d2242-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="d2242-452">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="d2242-453">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d2242-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="d2242-454">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="d2242-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d2242-455">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-455">The type of authentication to use.</span></span> <span data-ttu-id="d2242-456">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d2242-456">The possible values are:</span></span>

  - <span data-ttu-id="d2242-457">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d2242-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d2242-458">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="d2242-459">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d2242-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="d2242-460">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="d2242-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="d2242-461">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="d2242-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="d2242-462">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d2242-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="d2242-463">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d2242-464">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-465">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d2242-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="d2242-466">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d2242-467">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="d2242-468">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="d2242-469">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="d2242-470">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="d2242-471">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="d2242-472">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d2242-473">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d2242-474">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d2242-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="d2242-475">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-475">The Client ID for this project.</span></span> <span data-ttu-id="d2242-476">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d2242-477">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d2242-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="d2242-478">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="d2242-478">The domain for the directory tenant.</span></span> <span data-ttu-id="d2242-479">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-480">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d2242-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="d2242-481">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d2242-482">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d2242-483">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d2242-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="d2242-484">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="d2242-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d2242-485">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-486">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="d2242-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="d2242-487">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="d2242-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="d2242-488">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-489">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="d2242-490">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d2242-490">Turns off HTTPS.</span></span> <span data-ttu-id="d2242-491">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="d2242-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d2242-492">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d2242-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d2242-493">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-494">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-495">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="d2242-496">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-497">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-497">SDK version</span></span> | <span data-ttu-id="d2242-498">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-499">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-500">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="d2242-501">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="d2242-502">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="d2242-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="d2242-503">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2242-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="d2242-504">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="d2242-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="d2242-505">Параметр доступен начиная с пакета SDK для .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="d2242-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="d2242-506">angular, react</span><span class="sxs-lookup"><span data-stu-id="d2242-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d2242-507">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-507">The type of authentication to use.</span></span> <span data-ttu-id="d2242-508">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="d2242-509">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d2242-509">The possible values are:</span></span>

  - <span data-ttu-id="d2242-510">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d2242-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d2242-511">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-512">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-513">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="d2242-514">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d2242-514">Turns off HTTPS.</span></span> <span data-ttu-id="d2242-515">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="d2242-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d2242-516">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d2242-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d2242-517">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-518">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-519">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-520">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2242-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d2242-521">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-522">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-522">SDK version</span></span> | <span data-ttu-id="d2242-523">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-524">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-525">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d2242-526">2.1</span><span class="sxs-lookup"><span data-stu-id="d2242-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="d2242-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="d2242-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-528">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-529">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-530">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2242-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d2242-531">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-532">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-532">SDK version</span></span> | <span data-ttu-id="d2242-533">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-534">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-535">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d2242-536">2.1</span><span class="sxs-lookup"><span data-stu-id="d2242-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="d2242-537">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="d2242-538">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d2242-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="d2242-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="d2242-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2242-540">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="d2242-541">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="d2242-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="d2242-542">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2242-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="d2242-543">webapi</span><span class="sxs-lookup"><span data-stu-id="d2242-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d2242-544">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-544">The type of authentication to use.</span></span> <span data-ttu-id="d2242-545">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d2242-545">The possible values are:</span></span>

  - <span data-ttu-id="d2242-546">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d2242-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d2242-547">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d2242-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="d2242-548">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="d2242-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="d2242-549">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d2242-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="d2242-550">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d2242-551">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2242-552">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d2242-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="d2242-553">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d2242-554">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="d2242-555">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d2242-556">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d2242-557">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d2242-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="d2242-558">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d2242-558">The Client ID for this project.</span></span> <span data-ttu-id="d2242-559">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d2242-560">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d2242-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="d2242-561">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="d2242-561">The domain for the directory tenant.</span></span> <span data-ttu-id="d2242-562">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d2242-563">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d2242-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="d2242-564">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="d2242-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d2242-565">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d2242-566">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d2242-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="d2242-567">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="d2242-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="d2242-568">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2242-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d2242-569">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d2242-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="d2242-570">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d2242-570">Turns off HTTPS.</span></span> <span data-ttu-id="d2242-571">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="d2242-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="d2242-572">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2242-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d2242-573">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d2242-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d2242-574">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2242-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2242-575">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2242-576">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2242-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d2242-577">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="d2242-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d2242-578">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d2242-578">SDK version</span></span> | <span data-ttu-id="d2242-579">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d2242-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d2242-580">3.1</span><span class="sxs-lookup"><span data-stu-id="d2242-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d2242-581">3.0</span><span class="sxs-lookup"><span data-stu-id="d2242-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d2242-582">2.1</span><span class="sxs-lookup"><span data-stu-id="d2242-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="d2242-583">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d2242-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="d2242-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="d2242-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="d2242-585">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="d2242-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="d2242-586">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2242-586">Examples</span></span>

- <span data-ttu-id="d2242-587">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="d2242-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="d2242-588">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d2242-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="d2242-589">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="d2242-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="d2242-590">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="d2242-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="d2242-591">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="d2242-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="d2242-592">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="d2242-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="d2242-593">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="d2242-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="d2242-594">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="d2242-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="d2242-595">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="d2242-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="d2242-596">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="d2242-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="d2242-597">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="d2242-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="d2242-598">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="d2242-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="d2242-599">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="d2242-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="d2242-600">См. также</span><span class="sxs-lookup"><span data-stu-id="d2242-600">See also</span></span>

- [<span data-ttu-id="d2242-601">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2242-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="d2242-602">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="d2242-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="d2242-603">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="d2242-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="d2242-604">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2242-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
