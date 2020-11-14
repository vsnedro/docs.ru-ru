---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/04/2020
ms.openlocfilehash: 2ee06c37cd950f3b9771db2f30fe353435641d67
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400595"
---
# <a name="dotnet-new"></a><span data-ttu-id="e3d91-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e3d91-103">dotnet new</span></span>

<span data-ttu-id="e3d91-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e3d91-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e3d91-105">name</span><span class="sxs-lookup"><span data-stu-id="e3d91-105">Name</span></span>

<span data-ttu-id="e3d91-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e3d91-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e3d91-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="e3d91-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e3d91-108">Description</span></span>

<span data-ttu-id="e3d91-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="e3d91-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="e3d91-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="e3d91-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="e3d91-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e3d91-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="e3d91-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="e3d91-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e3d91-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="e3d91-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e3d91-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e3d91-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="e3d91-116">Вы можете запустить `dotnet new --list` или `dotnet new -l`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e3d91-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="e3d91-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="e3d91-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="e3d91-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="e3d91-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="e3d91-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="e3d91-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="e3d91-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="e3d91-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="e3d91-122">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e3d91-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="e3d91-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="e3d91-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="e3d91-124">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="e3d91-125">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="e3d91-125">Templates</span></span>                                    | <span data-ttu-id="e3d91-126">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="e3d91-126">Short name</span></span>                      | <span data-ttu-id="e3d91-127">Язык</span><span class="sxs-lookup"><span data-stu-id="e3d91-127">Language</span></span>     | <span data-ttu-id="e3d91-128">Tags</span><span class="sxs-lookup"><span data-stu-id="e3d91-128">Tags</span></span>                                  | <span data-ttu-id="e3d91-129">Введенный</span><span class="sxs-lookup"><span data-stu-id="e3d91-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="e3d91-130">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e3d91-130">Console Application</span></span>                          | [<span data-ttu-id="e3d91-131">Консоль</span><span class="sxs-lookup"><span data-stu-id="e3d91-131">console</span></span>](#console)             | <span data-ttu-id="e3d91-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-132">[C#], F#, VB</span></span> | <span data-ttu-id="e3d91-133">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="e3d91-133">Common/Console</span></span>                        | <span data-ttu-id="e3d91-134">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-134">1.0</span></span>        |
| <span data-ttu-id="e3d91-135">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="e3d91-135">Class library</span></span>                                | [<span data-ttu-id="e3d91-136">classlib</span><span class="sxs-lookup"><span data-stu-id="e3d91-136">classlib</span></span>](#classlib)           | <span data-ttu-id="e3d91-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-137">[C#], F#, VB</span></span> | <span data-ttu-id="e3d91-138">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="e3d91-138">Common/Library</span></span>                        | <span data-ttu-id="e3d91-139">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-139">1.0</span></span>        |
| <span data-ttu-id="e3d91-140">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-140">WPF Application</span></span>                              | [<span data-ttu-id="e3d91-141">wpf</span><span class="sxs-lookup"><span data-stu-id="e3d91-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="e3d91-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-142">[C#], VB</span></span>     | <span data-ttu-id="e3d91-143">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-143">Common/WPF</span></span>                            | <span data-ttu-id="e3d91-144">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="e3d91-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e3d91-145">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-145">WPF Class library</span></span>                            | [<span data-ttu-id="e3d91-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="e3d91-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="e3d91-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-147">[C#], VB</span></span>     | <span data-ttu-id="e3d91-148">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-148">Common/WPF</span></span>                            | <span data-ttu-id="e3d91-149">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="e3d91-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e3d91-150">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="e3d91-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="e3d91-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="e3d91-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-152">[C#], VB</span></span>     | <span data-ttu-id="e3d91-153">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-153">Common/WPF</span></span>                            | <span data-ttu-id="e3d91-154">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="e3d91-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e3d91-155">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="e3d91-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e3d91-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="e3d91-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-157">[C#], VB</span></span>     | <span data-ttu-id="e3d91-158">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="e3d91-158">Common/WPF</span></span>                            | <span data-ttu-id="e3d91-159">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="e3d91-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e3d91-160">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e3d91-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="e3d91-161">winforms</span><span class="sxs-lookup"><span data-stu-id="e3d91-161">winforms</span></span>](#winforms)           | <span data-ttu-id="e3d91-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-162">[C#], VB</span></span>     | <span data-ttu-id="e3d91-163">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e3d91-163">Common/WinForms</span></span>                       | <span data-ttu-id="e3d91-164">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="e3d91-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e3d91-165">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e3d91-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="e3d91-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="e3d91-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="e3d91-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-167">[C#], VB</span></span>     | <span data-ttu-id="e3d91-168">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e3d91-168">Common/WinForms</span></span>                       | <span data-ttu-id="e3d91-169">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="e3d91-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e3d91-170">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="e3d91-170">Worker Service</span></span>                               | [<span data-ttu-id="e3d91-171">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="e3d91-171">worker</span></span>](#web-others)           | <span data-ttu-id="e3d91-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-172">[C#]</span></span>         | <span data-ttu-id="e3d91-173">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="e3d91-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="e3d91-174">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-174">3.0</span></span>        |
| <span data-ttu-id="e3d91-175">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="e3d91-175">Unit Test Project</span></span>                            | [<span data-ttu-id="e3d91-176">mstest</span><span class="sxs-lookup"><span data-stu-id="e3d91-176">mstest</span></span>](#test)                 | <span data-ttu-id="e3d91-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-177">[C#], F#, VB</span></span> | <span data-ttu-id="e3d91-178">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="e3d91-178">Test/MSTest</span></span>                           | <span data-ttu-id="e3d91-179">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-179">1.0</span></span>        |
| <span data-ttu-id="e3d91-180">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e3d91-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="e3d91-181">nunit</span><span class="sxs-lookup"><span data-stu-id="e3d91-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="e3d91-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-182">[C#], F#, VB</span></span> | <span data-ttu-id="e3d91-183">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="e3d91-183">Test/NUnit</span></span>                            | <span data-ttu-id="e3d91-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="e3d91-184">2.1.400</span></span>    |
| <span data-ttu-id="e3d91-185">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e3d91-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="e3d91-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-186">[C#], F#, VB</span></span> | <span data-ttu-id="e3d91-187">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="e3d91-187">Test/NUnit</span></span>                            | <span data-ttu-id="e3d91-188">2.2</span><span class="sxs-lookup"><span data-stu-id="e3d91-188">2.2</span></span>        |
| <span data-ttu-id="e3d91-189">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="e3d91-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="e3d91-190">xunit</span><span class="sxs-lookup"><span data-stu-id="e3d91-190">xunit</span></span>](#test)                  | <span data-ttu-id="e3d91-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3d91-191">[C#], F#, VB</span></span> | <span data-ttu-id="e3d91-192">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="e3d91-192">Test/xUnit</span></span>                            | <span data-ttu-id="e3d91-193">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-193">1.0</span></span>        |
| <span data-ttu-id="e3d91-194">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="e3d91-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="e3d91-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-195">[C#]</span></span>         | <span data-ttu-id="e3d91-196">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e3d91-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="e3d91-197">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-197">3.0</span></span>        |
| <span data-ttu-id="e3d91-198">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="e3d91-198">Razor Page</span></span>                                   | [<span data-ttu-id="e3d91-199">page</span><span class="sxs-lookup"><span data-stu-id="e3d91-199">page</span></span>](#page)                   | <span data-ttu-id="e3d91-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-200">[C#]</span></span>         | <span data-ttu-id="e3d91-201">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e3d91-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="e3d91-202">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-202">2.0</span></span>        |
| <span data-ttu-id="e3d91-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e3d91-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="e3d91-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="e3d91-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="e3d91-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-205">[C#]</span></span>         | <span data-ttu-id="e3d91-206">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e3d91-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="e3d91-207">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-207">2.0</span></span>        |
| <span data-ttu-id="e3d91-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e3d91-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="e3d91-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-209">[C#]</span></span>         | <span data-ttu-id="e3d91-210">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e3d91-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="e3d91-211">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-211">2.0</span></span>        |
| <span data-ttu-id="e3d91-212">Серверное приложение :::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="e3d91-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="e3d91-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e3d91-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="e3d91-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-214">[C#]</span></span>         | <span data-ttu-id="e3d91-215">Веб/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="e3d91-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="e3d91-216">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-216">3.0</span></span>        |
| <span data-ttu-id="e3d91-217">Приложение :::no-loc(WebAssembly)::: :::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="e3d91-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | [<span data-ttu-id="e3d91-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="e3d91-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="e3d91-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-219">[C#]</span></span>         | <span data-ttu-id="e3d91-220">Веб/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="e3d91-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="e3d91-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="e3d91-221">3.1.300</span></span>    |
| <span data-ttu-id="e3d91-222">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e3d91-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="e3d91-223">web</span><span class="sxs-lookup"><span data-stu-id="e3d91-223">web</span></span>](#web)                     | <span data-ttu-id="e3d91-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3d91-224">[C#], F#</span></span>     | <span data-ttu-id="e3d91-225">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="e3d91-225">Web/Empty</span></span>                             | <span data-ttu-id="e3d91-226">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-226">1.0</span></span>        |
| <span data-ttu-id="e3d91-227">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e3d91-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="e3d91-228">mvc</span><span class="sxs-lookup"><span data-stu-id="e3d91-228">mvc</span></span>](#web-options)             | <span data-ttu-id="e3d91-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3d91-229">[C#], F#</span></span>     | <span data-ttu-id="e3d91-230">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="e3d91-230">Web/MVC</span></span>                               | <span data-ttu-id="e3d91-231">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-231">1.0</span></span>        |
| <span data-ttu-id="e3d91-232">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e3d91-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="e3d91-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="e3d91-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="e3d91-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-234">[C#]</span></span>         | <span data-ttu-id="e3d91-235">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="e3d91-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="e3d91-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="e3d91-237">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="e3d91-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="e3d91-238">angular</span><span class="sxs-lookup"><span data-stu-id="e3d91-238">angular</span></span>](#spa)                 | <span data-ttu-id="e3d91-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-239">[C#]</span></span>         | <span data-ttu-id="e3d91-240">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e3d91-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e3d91-241">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-241">2.0</span></span>        |
| <span data-ttu-id="e3d91-242">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="e3d91-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="e3d91-243">react</span><span class="sxs-lookup"><span data-stu-id="e3d91-243">react</span></span>](#spa)                   | <span data-ttu-id="e3d91-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-244">[C#]</span></span>         | <span data-ttu-id="e3d91-245">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e3d91-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e3d91-246">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-246">2.0</span></span>        |
| <span data-ttu-id="e3d91-247">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="e3d91-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="e3d91-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="e3d91-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="e3d91-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-249">[C#]</span></span>         | <span data-ttu-id="e3d91-250">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="e3d91-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e3d91-251">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-251">2.0</span></span>        |
| <span data-ttu-id="e3d91-252">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e3d91-252">Razor Class Library</span></span>                          | [<span data-ttu-id="e3d91-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e3d91-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="e3d91-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-254">[C#]</span></span>         | <span data-ttu-id="e3d91-255">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e3d91-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="e3d91-256">2.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-256">2.1</span></span>        |
| <span data-ttu-id="e3d91-257">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e3d91-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="e3d91-258">webapi</span><span class="sxs-lookup"><span data-stu-id="e3d91-258">webapi</span></span>](#webapi)               | <span data-ttu-id="e3d91-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3d91-259">[C#], F#</span></span>     | <span data-ttu-id="e3d91-260">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="e3d91-260">Web/WebAPI</span></span>                            | <span data-ttu-id="e3d91-261">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-261">1.0</span></span>        |
| <span data-ttu-id="e3d91-262">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e3d91-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="e3d91-263">grpc</span><span class="sxs-lookup"><span data-stu-id="e3d91-263">grpc</span></span>](#web-others)             | <span data-ttu-id="e3d91-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3d91-264">[C#]</span></span>         | <span data-ttu-id="e3d91-265">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="e3d91-265">Web/gRPC</span></span>                              | <span data-ttu-id="e3d91-266">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-266">3.0</span></span>        |
| <span data-ttu-id="e3d91-267">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="e3d91-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="e3d91-268">Config</span><span class="sxs-lookup"><span data-stu-id="e3d91-268">Config</span></span>                                | <span data-ttu-id="e3d91-269">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-269">3.0</span></span>        |
| <span data-ttu-id="e3d91-270">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="e3d91-270">global.json file</span></span>                             | [<span data-ttu-id="e3d91-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="e3d91-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="e3d91-272">Config</span><span class="sxs-lookup"><span data-stu-id="e3d91-272">Config</span></span>                                | <span data-ttu-id="e3d91-273">2.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-273">2.0</span></span>        |
| <span data-ttu-id="e3d91-274">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="e3d91-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="e3d91-275">Config</span><span class="sxs-lookup"><span data-stu-id="e3d91-275">Config</span></span>                                | <span data-ttu-id="e3d91-276">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-276">1.0</span></span>        |
| <span data-ttu-id="e3d91-277">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="e3d91-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="e3d91-278">Config</span><span class="sxs-lookup"><span data-stu-id="e3d91-278">Config</span></span>                                | <span data-ttu-id="e3d91-279">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-279">3.0</span></span>        |
| <span data-ttu-id="e3d91-280">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3d91-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="e3d91-281">Config</span><span class="sxs-lookup"><span data-stu-id="e3d91-281">Config</span></span>                                | <span data-ttu-id="e3d91-282">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-282">1.0</span></span>        |
| <span data-ttu-id="e3d91-283">Файл решения</span><span class="sxs-lookup"><span data-stu-id="e3d91-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="e3d91-284">Решение</span><span class="sxs-lookup"><span data-stu-id="e3d91-284">Solution</span></span>                              | <span data-ttu-id="e3d91-285">1.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-285">1.0</span></span>        |
| <span data-ttu-id="e3d91-286">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="e3d91-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="e3d91-287">proto</span><span class="sxs-lookup"><span data-stu-id="e3d91-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="e3d91-288">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="e3d91-288">Web/gRPC</span></span>                              | <span data-ttu-id="e3d91-289">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="e3d91-290">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3d91-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="e3d91-291">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="e3d91-292">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e3d91-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="e3d91-293">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="e3d91-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e3d91-294">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="e3d91-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e3d91-295">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="e3d91-295">Prints out help for the command.</span></span> <span data-ttu-id="e3d91-296">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="e3d91-297">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="e3d91-298">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e3d91-299">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e3d91-300">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="e3d91-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="e3d91-301">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="e3d91-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="e3d91-302">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="e3d91-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="e3d91-303">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="e3d91-304">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e3d91-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="e3d91-305">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e3d91-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="e3d91-306">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-306">The language of the template to create.</span></span> <span data-ttu-id="e3d91-307">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e3d91-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e3d91-308">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e3d91-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e3d91-309">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="e3d91-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e3d91-310">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="e3d91-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="e3d91-311">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="e3d91-312">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e3d91-312">The name for the created output.</span></span> <span data-ttu-id="e3d91-313">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="e3d91-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="e3d91-314">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="e3d91-314">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="e3d91-315">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="e3d91-315">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e3d91-316">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e3d91-316">Location to place the generated output.</span></span> <span data-ttu-id="e3d91-317">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e3d91-317">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="e3d91-318">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="e3d91-318">Filters templates based on available types.</span></span> <span data-ttu-id="e3d91-319">Предопределенные значения: `project` и `item`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-319">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="e3d91-320">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-320">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e3d91-321">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e3d91-321">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="e3d91-322">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-322">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="e3d91-323">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="e3d91-323">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e3d91-324">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="e3d91-324">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e3d91-325">Например, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp*  — нет.</span><span class="sxs-lookup"><span data-stu-id="e3d91-325">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="e3d91-326">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="e3d91-326">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="e3d91-327">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="e3d91-327">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="e3d91-328">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-328">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="e3d91-329">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e3d91-329">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="e3d91-330">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-330">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="e3d91-331">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="e3d91-331">Template options</span></span>

<span data-ttu-id="e3d91-332">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="e3d91-332">Each project template may have additional options available.</span></span> <span data-ttu-id="e3d91-333">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="e3d91-333">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="e3d91-334">console</span><span class="sxs-lookup"><span data-stu-id="e3d91-334">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e3d91-335">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-335">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-336">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-336">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e3d91-337">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-337">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-338">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-338">SDK version</span></span> | <span data-ttu-id="e3d91-339">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-339">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-340">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-341">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e3d91-342">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e3d91-343">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e3d91-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e3d91-344">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="e3d91-344">Not supported for F#.</span></span> <span data-ttu-id="e3d91-345">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e3d91-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e3d91-346">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e3d91-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-347">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="e3d91-348">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e3d91-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="e3d91-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="e3d91-350">classlib</span><span class="sxs-lookup"><span data-stu-id="e3d91-350">classlib</span></span>

- <span data-ttu-id="e3d91-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="e3d91-352">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-353">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="e3d91-353">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e3d91-354">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-354">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e3d91-355">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e3d91-356">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e3d91-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e3d91-357">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="e3d91-357">Not supported for F#.</span></span> <span data-ttu-id="e3d91-358">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e3d91-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e3d91-359">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e3d91-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-360">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="e3d91-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e3d91-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="e3d91-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="e3d91-364">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-365">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-365">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e3d91-366">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e3d91-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e3d91-367">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e3d91-368">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e3d91-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e3d91-369">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e3d91-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-370">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="e3d91-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="e3d91-372">winforms, winformslib</span></span>

- <span data-ttu-id="e3d91-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="e3d91-374">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e3d91-375">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e3d91-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e3d91-376">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e3d91-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-377">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="e3d91-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="e3d91-379">worker, grpc</span></span>

- <span data-ttu-id="e3d91-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="e3d91-381">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-382">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e3d91-383">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e3d91-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e3d91-384">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-385">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="e3d91-387">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="e3d91-387">mstest, xunit</span></span>

- <span data-ttu-id="e3d91-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="e3d91-389">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-390">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e3d91-391">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-392">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-392">SDK version</span></span> | <span data-ttu-id="e3d91-393">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-394">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-394">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-395">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-395">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e3d91-396">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-397">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-397">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-398">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-398">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="e3d91-399">nunit</span><span class="sxs-lookup"><span data-stu-id="e3d91-399">nunit</span></span>

- <span data-ttu-id="e3d91-400">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-400">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="e3d91-401">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-401">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e3d91-402">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-402">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-403">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-403">SDK version</span></span> | <span data-ttu-id="e3d91-404">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-404">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-405">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-405">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-406">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-406">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e3d91-407">2.2</span><span class="sxs-lookup"><span data-stu-id="e3d91-407">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="e3d91-408">2.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-408">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e3d91-409">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-409">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-410">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-410">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-411">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-411">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="e3d91-412">страница</span><span class="sxs-lookup"><span data-stu-id="e3d91-412">page</span></span>

- <span data-ttu-id="e3d91-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="e3d91-414">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="e3d91-414">Namespace for the generated code.</span></span> <span data-ttu-id="e3d91-415">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-415">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="e3d91-416">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="e3d91-416">Creates the page without a PageModel.</span></span>

<span data-ttu-id="e3d91-417">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-417">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="e3d91-418">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="e3d91-418">viewimports, proto</span></span>

- <span data-ttu-id="e3d91-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="e3d91-420">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="e3d91-420">Namespace for the generated code.</span></span> <span data-ttu-id="e3d91-421">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-421">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e3d91-422">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-422">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="e3d91-423">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e3d91-423">blazorserver</span></span>

- <span data-ttu-id="e3d91-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="e3d91-425">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-425">The type of authentication to use.</span></span> <span data-ttu-id="e3d91-426">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e3d91-426">The possible values are:</span></span>

  - <span data-ttu-id="e3d91-427">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3d91-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e3d91-428">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e3d91-429">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e3d91-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e3d91-430">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e3d91-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e3d91-431">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e3d91-431">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e3d91-432">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e3d91-432">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-433">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-433">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3d91-434">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-434">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-435">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-435">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e3d91-436">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-436">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3d91-437">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-437">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e3d91-438">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-438">The reset password policy ID for this project.</span></span> <span data-ttu-id="e3d91-439">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-439">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e3d91-440">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-440">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e3d91-441">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-441">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-442">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-442">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3d91-443">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-443">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3d91-444">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-444">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e3d91-445">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-445">The Client ID for this project.</span></span> <span data-ttu-id="e3d91-446">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-446">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3d91-447">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-447">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e3d91-448">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e3d91-448">The domain for the directory tenant.</span></span> <span data-ttu-id="e3d91-449">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-450">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-450">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e3d91-451">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-451">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3d91-452">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-452">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-453">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-453">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e3d91-454">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-454">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e3d91-455">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-456">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-456">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e3d91-457">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-457">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3d91-458">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-458">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e3d91-459">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-459">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-460">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-460">Turns off HTTPS.</span></span> <span data-ttu-id="e3d91-461">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-461">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e3d91-462">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e3d91-462">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3d91-463">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-463">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-464">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-464">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-465">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-465">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="e3d91-466">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="e3d91-466">blazorwasm</span></span>

- <span data-ttu-id="e3d91-467">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-467">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="e3d91-468">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e3d91-469">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-469">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-470">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-470">SDK version</span></span> | <span data-ttu-id="e3d91-471">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-471">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-472">5,0</span><span class="sxs-lookup"><span data-stu-id="e3d91-472">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e3d91-473">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-473">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="e3d91-474">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-474">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="e3d91-475">Включает узел ASP.NET Core для приложения :::no-loc(Blazor)::: :::no-loc(WebAssembly):::.</span><span class="sxs-lookup"><span data-stu-id="e3d91-475">Includes an ASP.NET Core host for the :::no-loc(Blazor)::: :::no-loc(WebAssembly)::: app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e3d91-476">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-476">The type of authentication to use.</span></span> <span data-ttu-id="e3d91-477">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e3d91-477">The possible values are:</span></span>

  - <span data-ttu-id="e3d91-478">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3d91-478">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e3d91-479">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-479">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e3d91-480">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e3d91-480">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e3d91-481">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e3d91-481">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="e3d91-482">Центр поставщика OIDC.</span><span class="sxs-lookup"><span data-stu-id="e3d91-482">The authority of the OIDC provider.</span></span> <span data-ttu-id="e3d91-483">Используется с проверкой подлинности `Individual`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-483">Use with `Individual` authentication.</span></span> <span data-ttu-id="e3d91-484">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-484">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-485">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-485">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3d91-486">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-486">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-487">Значение по умолчанию — `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-487">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e3d91-488">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-488">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3d91-489">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-489">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-490">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-490">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3d91-491">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-491">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-492">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-492">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e3d91-493">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-493">The Client ID for this project.</span></span> <span data-ttu-id="e3d91-494">Используйте для проверки подлинности `IndividualB2C`, `SingleOrg` или `Individual` в автономных сценариях.</span><span class="sxs-lookup"><span data-stu-id="e3d91-494">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="e3d91-495">Значение по умолчанию — `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-495">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e3d91-496">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e3d91-496">The domain for the directory tenant.</span></span> <span data-ttu-id="e3d91-497">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-497">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-498">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-498">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="e3d91-499">URI идентификатора приложения для серверного API-интерфейса, который требуется вызвать.</span><span class="sxs-lookup"><span data-stu-id="e3d91-499">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="e3d91-500">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-500">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-501">Значение по умолчанию — `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-501">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="e3d91-502">Идентификатор клиента для API, размещенного на сервере.</span><span class="sxs-lookup"><span data-stu-id="e3d91-502">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="e3d91-503">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-503">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-504">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-504">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="e3d91-505">Область API, которую клиент должен запросить для подготовки маркера доступа.</span><span class="sxs-lookup"><span data-stu-id="e3d91-505">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="e3d91-506">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-506">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-507">Значение по умолчанию — `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-507">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e3d91-508">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-508">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3d91-509">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-509">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-510">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-510">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e3d91-511">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-511">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3d91-512">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-512">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e3d91-513">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="e3d91-514">Создает прогрессивное веб-приложение (PWA), поддерживающее установку и автономное использование.</span><span class="sxs-lookup"><span data-stu-id="e3d91-514">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-515">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-515">Turns off HTTPS.</span></span> <span data-ttu-id="e3d91-516">Этот параметр применяется, только если `Individual`, `IndividualB2C` или `SingleOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-516">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e3d91-517">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e3d91-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3d91-518">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="e3d91-519">URL-адрес API для вызова из веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-519">URL of the API to call from the web app.</span></span> <span data-ttu-id="e3d91-520">Применяется только при проверке подлинности `SingleOrg` или `IndividualB2C` без указания узла ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e3d91-520">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="e3d91-521">Значение по умолчанию — `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-521">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="e3d91-522">Указывает, вызывает ли веб-приложение Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e3d91-522">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="e3d91-523">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-523">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="e3d91-524">Области для запроса вызова API из веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-524">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="e3d91-525">Применяется только при проверке подлинности `SingleOrg` или `IndividualB2C` без указания узла ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e3d91-525">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="e3d91-526">Значение по умолчанию — `user.read`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-526">The default is `user.read`.</span></span>

<span data-ttu-id="e3d91-527">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-527">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="e3d91-528">web</span><span class="sxs-lookup"><span data-stu-id="e3d91-528">web</span></span>

- <span data-ttu-id="e3d91-529">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-529">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="e3d91-530">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e3d91-531">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-532">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e3d91-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e3d91-533">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-534">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-534">SDK version</span></span> | <span data-ttu-id="e3d91-535">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-536">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-537">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e3d91-538">2.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-538">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e3d91-539">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-540">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-540">Turns off HTTPS.</span></span>

<span data-ttu-id="e3d91-541">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-541">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="e3d91-542">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="e3d91-542">mvc, webapp</span></span>

- <span data-ttu-id="e3d91-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="e3d91-544">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-544">The type of authentication to use.</span></span> <span data-ttu-id="e3d91-545">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e3d91-545">The possible values are:</span></span>

  - <span data-ttu-id="e3d91-546">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3d91-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e3d91-547">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-547">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e3d91-548">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e3d91-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e3d91-549">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e3d91-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e3d91-550">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e3d91-550">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e3d91-551">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e3d91-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-552">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3d91-553">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-554">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e3d91-555">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3d91-556">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-556">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e3d91-557">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-557">The reset password policy ID for this project.</span></span> <span data-ttu-id="e3d91-558">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-558">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e3d91-559">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-559">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e3d91-560">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-560">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-561">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-561">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3d91-562">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-562">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3d91-563">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-563">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e3d91-564">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-564">The Client ID for this project.</span></span> <span data-ttu-id="e3d91-565">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-565">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3d91-566">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-566">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e3d91-567">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e3d91-567">The domain for the directory tenant.</span></span> <span data-ttu-id="e3d91-568">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-568">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-569">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-569">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e3d91-570">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-570">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3d91-571">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-571">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-572">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-572">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e3d91-573">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-573">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e3d91-574">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-574">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-575">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-575">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e3d91-576">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-576">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3d91-577">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-577">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e3d91-578">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-578">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-579">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-579">Turns off HTTPS.</span></span> <span data-ttu-id="e3d91-580">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="e3d91-580">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e3d91-581">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e3d91-581">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3d91-582">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-582">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e3d91-583">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-583">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-584">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-584">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e3d91-585">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-585">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-586">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-586">SDK version</span></span> | <span data-ttu-id="e3d91-587">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-587">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-588">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-588">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-589">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-589">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="e3d91-590">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-590">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="e3d91-591">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="e3d91-591">Includes BrowserLink in the project.</span></span> <span data-ttu-id="e3d91-592">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e3d91-592">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="e3d91-593">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="e3d91-593">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="e3d91-594">Параметр доступен начиная с пакета SDK для .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="e3d91-594">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="e3d91-595">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-595">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="e3d91-596">angular, react</span><span class="sxs-lookup"><span data-stu-id="e3d91-596">angular, react</span></span>

- <span data-ttu-id="e3d91-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="e3d91-598">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-598">The type of authentication to use.</span></span> <span data-ttu-id="e3d91-599">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-599">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="e3d91-600">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e3d91-600">The possible values are:</span></span>

  - <span data-ttu-id="e3d91-601">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3d91-601">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e3d91-602">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-602">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e3d91-603">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e3d91-604">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-604">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-605">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-605">Turns off HTTPS.</span></span> <span data-ttu-id="e3d91-606">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-606">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e3d91-607">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e3d91-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3d91-608">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-608">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-609">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-609">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e3d91-610">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-610">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-611">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e3d91-611">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e3d91-612">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-612">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-613">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-613">SDK version</span></span> | <span data-ttu-id="e3d91-614">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-614">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-615">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-616">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e3d91-617">2.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-617">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="e3d91-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-618">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="e3d91-619">reactredux</span><span class="sxs-lookup"><span data-stu-id="e3d91-619">reactredux</span></span>

- <span data-ttu-id="e3d91-620">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-620">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="e3d91-621">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-621">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e3d91-622">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-622">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-623">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e3d91-623">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e3d91-624">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-624">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-625">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-625">SDK version</span></span> | <span data-ttu-id="e3d91-626">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-626">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-627">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-627">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-628">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-628">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e3d91-629">2.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-629">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="e3d91-630">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-630">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-631">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-631">Turns off HTTPS.</span></span>

<span data-ttu-id="e3d91-632">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-632">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="e3d91-633">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e3d91-633">razorclasslib</span></span>

- <span data-ttu-id="e3d91-634">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-634">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="e3d91-635">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-635">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="e3d91-636">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e3d91-636">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="e3d91-637">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3d91-637">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="e3d91-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-638">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="e3d91-639">webapi</span><span class="sxs-lookup"><span data-stu-id="e3d91-639">webapi</span></span>

- <span data-ttu-id="e3d91-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="e3d91-641">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-641">The type of authentication to use.</span></span> <span data-ttu-id="e3d91-642">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e3d91-642">The possible values are:</span></span>

  - <span data-ttu-id="e3d91-643">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3d91-643">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e3d91-644">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e3d91-644">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e3d91-645">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e3d91-645">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e3d91-646">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e3d91-646">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-647">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-647">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3d91-648">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-648">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3d91-649">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-649">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e3d91-650">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-650">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3d91-651">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-651">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e3d91-652">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-652">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3d91-653">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-653">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-654">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-654">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e3d91-655">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e3d91-655">The Client ID for this project.</span></span> <span data-ttu-id="e3d91-656">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-656">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-657">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-657">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e3d91-658">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e3d91-658">The domain for the directory tenant.</span></span> <span data-ttu-id="e3d91-659">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-659">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-660">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-660">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e3d91-661">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e3d91-661">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3d91-662">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-662">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3d91-663">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-663">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e3d91-664">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e3d91-664">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3d91-665">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-665">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e3d91-666">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e3d91-666">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e3d91-667">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e3d91-667">Turns off HTTPS.</span></span> <span data-ttu-id="e3d91-668">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-668">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e3d91-669">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3d91-669">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e3d91-670">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e3d91-670">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3d91-671">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e3d91-671">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e3d91-672">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e3d91-672">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3d91-673">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e3d91-673">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e3d91-674">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="e3d91-674">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e3d91-675">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="e3d91-675">SDK version</span></span> | <span data-ttu-id="e3d91-676">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d91-676">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e3d91-677">3.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-677">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e3d91-678">3.0</span><span class="sxs-lookup"><span data-stu-id="e3d91-678">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e3d91-679">2.1</span><span class="sxs-lookup"><span data-stu-id="e3d91-679">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e3d91-680">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e3d91-680">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3d91-681">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e3d91-681">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="e3d91-682">globaljson</span><span class="sxs-lookup"><span data-stu-id="e3d91-682">globaljson</span></span>

- <span data-ttu-id="e3d91-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="e3d91-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="e3d91-684">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e3d91-684">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="e3d91-685">Примеры</span><span class="sxs-lookup"><span data-stu-id="e3d91-685">Examples</span></span>

- <span data-ttu-id="e3d91-686">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="e3d91-686">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="e3d91-687">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="e3d91-687">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="e3d91-688">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="e3d91-688">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="e3d91-689">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="e3d91-689">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="e3d91-690">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="e3d91-690">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="e3d91-691">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="e3d91-691">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="e3d91-692">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="e3d91-692">List all templates matching the *we* substring.</span></span> <span data-ttu-id="e3d91-693">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="e3d91-693">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="e3d91-694">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="e3d91-694">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="e3d91-695">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="e3d91-695">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="e3d91-696">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="e3d91-696">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="e3d91-697">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="e3d91-697">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="e3d91-698">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="e3d91-698">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="e3d91-699">См. также</span><span class="sxs-lookup"><span data-stu-id="e3d91-699">See also</span></span>

- [<span data-ttu-id="e3d91-700">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e3d91-700">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="e3d91-701">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="e3d91-701">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="e3d91-702">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="e3d91-702">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="e3d91-703">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e3d91-703">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
