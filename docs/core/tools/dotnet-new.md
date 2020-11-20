---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET на основе указанного шаблона.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634459"
---
# <a name="dotnet-new"></a><span data-ttu-id="2a28f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2a28f-103">dotnet new</span></span>

<span data-ttu-id="2a28f-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="2a28f-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2a28f-105">name</span><span class="sxs-lookup"><span data-stu-id="2a28f-105">Name</span></span>

<span data-ttu-id="2a28f-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2a28f-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2a28f-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="2a28f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2a28f-108">Description</span></span>

<span data-ttu-id="2a28f-109">Команда `dotnet new` создает проект .NET или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="2a28f-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="2a28f-111">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="2a28f-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="2a28f-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2a28f-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="2a28f-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="2a28f-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="2a28f-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="2a28f-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="2a28f-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="2a28f-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="2a28f-116">Вы можете запустить `dotnet new --list` или `dotnet new -l`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="2a28f-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="2a28f-117">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="2a28f-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="2a28f-118">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="2a28f-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="2a28f-119">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="2a28f-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="2a28f-120">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="2a28f-121">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="2a28f-122">В следующей таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="2a28f-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="2a28f-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="2a28f-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="2a28f-124">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="2a28f-125">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="2a28f-125">Templates</span></span>                                    | <span data-ttu-id="2a28f-126">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="2a28f-126">Short name</span></span>                      | <span data-ttu-id="2a28f-127">Язык</span><span class="sxs-lookup"><span data-stu-id="2a28f-127">Language</span></span>     | <span data-ttu-id="2a28f-128">Tags</span><span class="sxs-lookup"><span data-stu-id="2a28f-128">Tags</span></span>                                  | <span data-ttu-id="2a28f-129">Введенный</span><span class="sxs-lookup"><span data-stu-id="2a28f-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="2a28f-130">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="2a28f-130">Console Application</span></span>                          | [<span data-ttu-id="2a28f-131">Консоль</span><span class="sxs-lookup"><span data-stu-id="2a28f-131">console</span></span>](#console)             | <span data-ttu-id="2a28f-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-132">[C#], F#, VB</span></span> | <span data-ttu-id="2a28f-133">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="2a28f-133">Common/Console</span></span>                        | <span data-ttu-id="2a28f-134">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-134">1.0</span></span>        |
| <span data-ttu-id="2a28f-135">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="2a28f-135">Class library</span></span>                                | [<span data-ttu-id="2a28f-136">classlib</span><span class="sxs-lookup"><span data-stu-id="2a28f-136">classlib</span></span>](#classlib)           | <span data-ttu-id="2a28f-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-137">[C#], F#, VB</span></span> | <span data-ttu-id="2a28f-138">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="2a28f-138">Common/Library</span></span>                        | <span data-ttu-id="2a28f-139">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-139">1.0</span></span>        |
| <span data-ttu-id="2a28f-140">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-140">WPF Application</span></span>                              | [<span data-ttu-id="2a28f-141">wpf</span><span class="sxs-lookup"><span data-stu-id="2a28f-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="2a28f-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-142">[C#], VB</span></span>     | <span data-ttu-id="2a28f-143">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-143">Common/WPF</span></span>                            | <span data-ttu-id="2a28f-144">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="2a28f-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="2a28f-145">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-145">WPF Class library</span></span>                            | [<span data-ttu-id="2a28f-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="2a28f-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="2a28f-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-147">[C#], VB</span></span>     | <span data-ttu-id="2a28f-148">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-148">Common/WPF</span></span>                            | <span data-ttu-id="2a28f-149">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="2a28f-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="2a28f-150">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="2a28f-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="2a28f-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="2a28f-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-152">[C#], VB</span></span>     | <span data-ttu-id="2a28f-153">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-153">Common/WPF</span></span>                            | <span data-ttu-id="2a28f-154">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="2a28f-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="2a28f-155">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="2a28f-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="2a28f-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="2a28f-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-157">[C#], VB</span></span>     | <span data-ttu-id="2a28f-158">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="2a28f-158">Common/WPF</span></span>                            | <span data-ttu-id="2a28f-159">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="2a28f-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="2a28f-160">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="2a28f-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="2a28f-161">winforms</span><span class="sxs-lookup"><span data-stu-id="2a28f-161">winforms</span></span>](#winforms)           | <span data-ttu-id="2a28f-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-162">[C#], VB</span></span>     | <span data-ttu-id="2a28f-163">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="2a28f-163">Common/WinForms</span></span>                       | <span data-ttu-id="2a28f-164">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="2a28f-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="2a28f-165">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="2a28f-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="2a28f-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="2a28f-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="2a28f-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-167">[C#], VB</span></span>     | <span data-ttu-id="2a28f-168">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="2a28f-168">Common/WinForms</span></span>                       | <span data-ttu-id="2a28f-169">3.0 (5.0 для VB)</span><span class="sxs-lookup"><span data-stu-id="2a28f-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="2a28f-170">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="2a28f-170">Worker Service</span></span>                               | [<span data-ttu-id="2a28f-171">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="2a28f-171">worker</span></span>](#web-others)           | <span data-ttu-id="2a28f-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-172">[C#]</span></span>         | <span data-ttu-id="2a28f-173">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="2a28f-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="2a28f-174">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-174">3.0</span></span>        |
| <span data-ttu-id="2a28f-175">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="2a28f-175">Unit Test Project</span></span>                            | [<span data-ttu-id="2a28f-176">mstest</span><span class="sxs-lookup"><span data-stu-id="2a28f-176">mstest</span></span>](#test)                 | <span data-ttu-id="2a28f-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-177">[C#], F#, VB</span></span> | <span data-ttu-id="2a28f-178">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="2a28f-178">Test/MSTest</span></span>                           | <span data-ttu-id="2a28f-179">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-179">1.0</span></span>        |
| <span data-ttu-id="2a28f-180">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="2a28f-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="2a28f-181">nunit</span><span class="sxs-lookup"><span data-stu-id="2a28f-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="2a28f-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-182">[C#], F#, VB</span></span> | <span data-ttu-id="2a28f-183">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="2a28f-183">Test/NUnit</span></span>                            | <span data-ttu-id="2a28f-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="2a28f-184">2.1.400</span></span>    |
| <span data-ttu-id="2a28f-185">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="2a28f-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="2a28f-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-186">[C#], F#, VB</span></span> | <span data-ttu-id="2a28f-187">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="2a28f-187">Test/NUnit</span></span>                            | <span data-ttu-id="2a28f-188">2.2</span><span class="sxs-lookup"><span data-stu-id="2a28f-188">2.2</span></span>        |
| <span data-ttu-id="2a28f-189">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="2a28f-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="2a28f-190">xunit</span><span class="sxs-lookup"><span data-stu-id="2a28f-190">xunit</span></span>](#test)                  | <span data-ttu-id="2a28f-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2a28f-191">[C#], F#, VB</span></span> | <span data-ttu-id="2a28f-192">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="2a28f-192">Test/xUnit</span></span>                            | <span data-ttu-id="2a28f-193">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-193">1.0</span></span>        |
| <span data-ttu-id="2a28f-194">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="2a28f-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="2a28f-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-195">[C#]</span></span>         | <span data-ttu-id="2a28f-196">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2a28f-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="2a28f-197">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-197">3.0</span></span>        |
| <span data-ttu-id="2a28f-198">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="2a28f-198">Razor Page</span></span>                                   | [<span data-ttu-id="2a28f-199">page</span><span class="sxs-lookup"><span data-stu-id="2a28f-199">page</span></span>](#page)                   | <span data-ttu-id="2a28f-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-200">[C#]</span></span>         | <span data-ttu-id="2a28f-201">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2a28f-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="2a28f-202">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-202">2.0</span></span>        |
| <span data-ttu-id="2a28f-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="2a28f-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="2a28f-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="2a28f-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="2a28f-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-205">[C#]</span></span>         | <span data-ttu-id="2a28f-206">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2a28f-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="2a28f-207">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-207">2.0</span></span>        |
| <span data-ttu-id="2a28f-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="2a28f-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="2a28f-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-209">[C#]</span></span>         | <span data-ttu-id="2a28f-210">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2a28f-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="2a28f-211">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-211">2.0</span></span>        |
| <span data-ttu-id="2a28f-212">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="2a28f-212">Blazor Server App</span></span>                            | [<span data-ttu-id="2a28f-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="2a28f-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="2a28f-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-214">[C#]</span></span>         | <span data-ttu-id="2a28f-215">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="2a28f-215">Web/Blazor</span></span>                            | <span data-ttu-id="2a28f-216">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-216">3.0</span></span>        |
| <span data-ttu-id="2a28f-217">Приложение WebAssembly Blazor</span><span class="sxs-lookup"><span data-stu-id="2a28f-217">Blazor WebAssembly App</span></span>                       | [<span data-ttu-id="2a28f-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="2a28f-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="2a28f-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-219">[C#]</span></span>         | <span data-ttu-id="2a28f-220">Веб/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="2a28f-220">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="2a28f-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="2a28f-221">3.1.300</span></span>    |
| <span data-ttu-id="2a28f-222">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2a28f-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="2a28f-223">web</span><span class="sxs-lookup"><span data-stu-id="2a28f-223">web</span></span>](#web)                     | <span data-ttu-id="2a28f-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="2a28f-224">[C#], F#</span></span>     | <span data-ttu-id="2a28f-225">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="2a28f-225">Web/Empty</span></span>                             | <span data-ttu-id="2a28f-226">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-226">1.0</span></span>        |
| <span data-ttu-id="2a28f-227">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="2a28f-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="2a28f-228">mvc</span><span class="sxs-lookup"><span data-stu-id="2a28f-228">mvc</span></span>](#web-options)             | <span data-ttu-id="2a28f-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="2a28f-229">[C#], F#</span></span>     | <span data-ttu-id="2a28f-230">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="2a28f-230">Web/MVC</span></span>                               | <span data-ttu-id="2a28f-231">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-231">1.0</span></span>        |
| <span data-ttu-id="2a28f-232">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2a28f-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="2a28f-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="2a28f-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="2a28f-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-234">[C#]</span></span>         | <span data-ttu-id="2a28f-235">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="2a28f-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="2a28f-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="2a28f-237">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="2a28f-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="2a28f-238">angular</span><span class="sxs-lookup"><span data-stu-id="2a28f-238">angular</span></span>](#spa)                 | <span data-ttu-id="2a28f-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-239">[C#]</span></span>         | <span data-ttu-id="2a28f-240">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="2a28f-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="2a28f-241">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-241">2.0</span></span>        |
| <span data-ttu-id="2a28f-242">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="2a28f-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="2a28f-243">react</span><span class="sxs-lookup"><span data-stu-id="2a28f-243">react</span></span>](#spa)                   | <span data-ttu-id="2a28f-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-244">[C#]</span></span>         | <span data-ttu-id="2a28f-245">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="2a28f-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="2a28f-246">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-246">2.0</span></span>        |
| <span data-ttu-id="2a28f-247">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="2a28f-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="2a28f-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="2a28f-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="2a28f-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-249">[C#]</span></span>         | <span data-ttu-id="2a28f-250">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="2a28f-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="2a28f-251">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-251">2.0</span></span>        |
| <span data-ttu-id="2a28f-252">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="2a28f-252">Razor Class Library</span></span>                          | [<span data-ttu-id="2a28f-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="2a28f-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="2a28f-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-254">[C#]</span></span>         | <span data-ttu-id="2a28f-255">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="2a28f-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="2a28f-256">2.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-256">2.1</span></span>        |
| <span data-ttu-id="2a28f-257">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2a28f-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="2a28f-258">webapi</span><span class="sxs-lookup"><span data-stu-id="2a28f-258">webapi</span></span>](#webapi)               | <span data-ttu-id="2a28f-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="2a28f-259">[C#], F#</span></span>     | <span data-ttu-id="2a28f-260">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="2a28f-260">Web/WebAPI</span></span>                            | <span data-ttu-id="2a28f-261">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-261">1.0</span></span>        |
| <span data-ttu-id="2a28f-262">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="2a28f-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="2a28f-263">grpc</span><span class="sxs-lookup"><span data-stu-id="2a28f-263">grpc</span></span>](#web-others)             | <span data-ttu-id="2a28f-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="2a28f-264">[C#]</span></span>         | <span data-ttu-id="2a28f-265">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="2a28f-265">Web/gRPC</span></span>                              | <span data-ttu-id="2a28f-266">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-266">3.0</span></span>        |
| <span data-ttu-id="2a28f-267">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="2a28f-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="2a28f-268">Config</span><span class="sxs-lookup"><span data-stu-id="2a28f-268">Config</span></span>                                | <span data-ttu-id="2a28f-269">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-269">3.0</span></span>        |
| <span data-ttu-id="2a28f-270">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="2a28f-270">global.json file</span></span>                             | [<span data-ttu-id="2a28f-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="2a28f-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="2a28f-272">Config</span><span class="sxs-lookup"><span data-stu-id="2a28f-272">Config</span></span>                                | <span data-ttu-id="2a28f-273">2.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-273">2.0</span></span>        |
| <span data-ttu-id="2a28f-274">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="2a28f-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="2a28f-275">Config</span><span class="sxs-lookup"><span data-stu-id="2a28f-275">Config</span></span>                                | <span data-ttu-id="2a28f-276">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-276">1.0</span></span>        |
| <span data-ttu-id="2a28f-277">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="2a28f-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="2a28f-278">Config</span><span class="sxs-lookup"><span data-stu-id="2a28f-278">Config</span></span>                                | <span data-ttu-id="2a28f-279">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-279">3.0</span></span>        |
| <span data-ttu-id="2a28f-280">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="2a28f-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="2a28f-281">Config</span><span class="sxs-lookup"><span data-stu-id="2a28f-281">Config</span></span>                                | <span data-ttu-id="2a28f-282">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-282">1.0</span></span>        |
| <span data-ttu-id="2a28f-283">Файл решения</span><span class="sxs-lookup"><span data-stu-id="2a28f-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="2a28f-284">Решение</span><span class="sxs-lookup"><span data-stu-id="2a28f-284">Solution</span></span>                              | <span data-ttu-id="2a28f-285">1.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-285">1.0</span></span>        |
| <span data-ttu-id="2a28f-286">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="2a28f-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="2a28f-287">proto</span><span class="sxs-lookup"><span data-stu-id="2a28f-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="2a28f-288">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="2a28f-288">Web/gRPC</span></span>                              | <span data-ttu-id="2a28f-289">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="2a28f-290">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a28f-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="2a28f-291">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="2a28f-292">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="2a28f-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="2a28f-293">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="2a28f-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="2a28f-294">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="2a28f-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2a28f-295">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="2a28f-295">Prints out help for the command.</span></span> <span data-ttu-id="2a28f-296">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="2a28f-297">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="2a28f-298">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="2a28f-299">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="2a28f-300">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="2a28f-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="2a28f-301">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="2a28f-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="2a28f-302">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="2a28f-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="2a28f-303">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="2a28f-304">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="2a28f-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="2a28f-305">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="2a28f-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="2a28f-306">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-306">The language of the template to create.</span></span> <span data-ttu-id="2a28f-307">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="2a28f-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="2a28f-308">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="2a28f-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2a28f-309">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="2a28f-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="2a28f-310">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="2a28f-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="2a28f-311">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="2a28f-312">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2a28f-312">The name for the created output.</span></span> <span data-ttu-id="2a28f-313">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="2a28f-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="2a28f-314">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="2a28f-314">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="2a28f-315">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2a28f-315">Location to place the generated output.</span></span> <span data-ttu-id="2a28f-316">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="2a28f-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="2a28f-317">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="2a28f-317">Filters templates based on available types.</span></span> <span data-ttu-id="2a28f-318">Предопределенные значения: `project` и `item`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="2a28f-319">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="2a28f-320">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="2a28f-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="2a28f-321">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="2a28f-322">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="2a28f-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2a28f-323">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="2a28f-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="2a28f-324">Например, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="2a28f-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="2a28f-325">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="2a28f-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="2a28f-326">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="2a28f-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="2a28f-327">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="2a28f-328">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="2a28f-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="2a28f-329">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="2a28f-330">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="2a28f-330">Template options</span></span>

<span data-ttu-id="2a28f-331">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="2a28f-331">Each project template may have additional options available.</span></span> <span data-ttu-id="2a28f-332">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="2a28f-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="2a28f-333">console</span><span class="sxs-lookup"><span data-stu-id="2a28f-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2a28f-334">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-335">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="2a28f-336">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-337">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-337">SDK version</span></span> | <span data-ttu-id="2a28f-338">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-339">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-339">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-340">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-341">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2a28f-342">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2a28f-343">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="2a28f-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="2a28f-344">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="2a28f-344">Not supported for F#.</span></span> <span data-ttu-id="2a28f-345">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="2a28f-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2a28f-346">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="2a28f-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-347">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="2a28f-348">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="2a28f-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="2a28f-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="2a28f-350">classlib</span><span class="sxs-lookup"><span data-stu-id="2a28f-350">classlib</span></span>

- <span data-ttu-id="2a28f-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="2a28f-352">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-353">Значения: `net5.0` или `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="2a28f-353">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="2a28f-354">Значение по умолчанию для пакета SDK для .NET 5.0 — `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-354">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2a28f-355">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2a28f-356">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="2a28f-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="2a28f-357">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="2a28f-357">Not supported for F#.</span></span> <span data-ttu-id="2a28f-358">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="2a28f-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2a28f-359">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="2a28f-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-360">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="2a28f-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="2a28f-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="2a28f-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="2a28f-364">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-365">Значение по умолчанию — `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-365">The default value is `net5.0`.</span></span> <span data-ttu-id="2a28f-366">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2a28f-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2a28f-367">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2a28f-368">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="2a28f-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="2a28f-369">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="2a28f-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-370">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="2a28f-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="2a28f-372">winforms, winformslib</span></span>

- <span data-ttu-id="2a28f-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="2a28f-374">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2a28f-375">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="2a28f-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="2a28f-376">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="2a28f-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-377">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="2a28f-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="2a28f-379">worker, grpc</span></span>

- <span data-ttu-id="2a28f-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="2a28f-381">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-382">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="2a28f-383">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2a28f-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2a28f-384">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-385">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="2a28f-387">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="2a28f-387">mstest, xunit</span></span>

- <span data-ttu-id="2a28f-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="2a28f-389">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-390">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="2a28f-391">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-392">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-392">SDK version</span></span> | <span data-ttu-id="2a28f-393">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-394">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-394">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-395">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-395">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-396">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-396">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="2a28f-397">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-397">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-398">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-398">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-399">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-399">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="2a28f-400">nunit</span><span class="sxs-lookup"><span data-stu-id="2a28f-400">nunit</span></span>

- <span data-ttu-id="2a28f-401">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-401">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="2a28f-402">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-402">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="2a28f-403">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-403">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-404">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-404">SDK version</span></span> | <span data-ttu-id="2a28f-405">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-405">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-406">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-406">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-407">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-407">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-408">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-408">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2a28f-409">2.2</span><span class="sxs-lookup"><span data-stu-id="2a28f-409">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="2a28f-410">2.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-410">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="2a28f-411">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-411">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-412">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-412">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-413">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-413">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="2a28f-414">страница</span><span class="sxs-lookup"><span data-stu-id="2a28f-414">page</span></span>

- <span data-ttu-id="2a28f-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="2a28f-416">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="2a28f-416">Namespace for the generated code.</span></span> <span data-ttu-id="2a28f-417">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-417">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="2a28f-418">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="2a28f-418">Creates the page without a PageModel.</span></span>

<span data-ttu-id="2a28f-419">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-419">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="2a28f-420">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="2a28f-420">viewimports, proto</span></span>

- <span data-ttu-id="2a28f-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="2a28f-422">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="2a28f-422">Namespace for the generated code.</span></span> <span data-ttu-id="2a28f-423">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-423">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="2a28f-424">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-424">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="2a28f-425">blazorserver</span><span class="sxs-lookup"><span data-stu-id="2a28f-425">blazorserver</span></span>

- <span data-ttu-id="2a28f-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="2a28f-427">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-427">The type of authentication to use.</span></span> <span data-ttu-id="2a28f-428">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2a28f-428">The possible values are:</span></span>

  - <span data-ttu-id="2a28f-429">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a28f-429">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2a28f-430">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-430">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="2a28f-431">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="2a28f-431">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2a28f-432">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="2a28f-432">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="2a28f-433">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a28f-433">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="2a28f-434">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="2a28f-434">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-435">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-435">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2a28f-436">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-436">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-437">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-437">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2a28f-438">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-438">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2a28f-439">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-439">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="2a28f-440">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-440">The reset password policy ID for this project.</span></span> <span data-ttu-id="2a28f-441">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-441">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="2a28f-442">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-442">The edit profile policy ID for this project.</span></span> <span data-ttu-id="2a28f-443">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-443">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-444">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-444">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2a28f-445">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-445">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="2a28f-446">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-446">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2a28f-447">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-447">The Client ID for this project.</span></span> <span data-ttu-id="2a28f-448">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-448">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="2a28f-449">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-449">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2a28f-450">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="2a28f-450">The domain for the directory tenant.</span></span> <span data-ttu-id="2a28f-451">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-451">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-452">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-452">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2a28f-453">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-453">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2a28f-454">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-454">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-455">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-455">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="2a28f-456">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-456">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="2a28f-457">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-457">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-458">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-458">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2a28f-459">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-459">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2a28f-460">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-460">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2a28f-461">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-461">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-462">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-462">Turns off HTTPS.</span></span> <span data-ttu-id="2a28f-463">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-463">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2a28f-464">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2a28f-464">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2a28f-465">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-465">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-466">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-466">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-467">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-467">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="2a28f-468">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="2a28f-468">blazorwasm</span></span>

- <span data-ttu-id="2a28f-469">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-469">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="2a28f-470">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-470">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="2a28f-471">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-471">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-472">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-472">SDK version</span></span> | <span data-ttu-id="2a28f-473">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-473">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-474">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-474">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-475">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-475">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="2a28f-476">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="2a28f-477">Включает узел ASP.NET Core для приложения Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="2a28f-477">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="2a28f-478">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-478">The type of authentication to use.</span></span> <span data-ttu-id="2a28f-479">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2a28f-479">The possible values are:</span></span>

  - <span data-ttu-id="2a28f-480">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a28f-480">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2a28f-481">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-481">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="2a28f-482">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="2a28f-482">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2a28f-483">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="2a28f-483">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="2a28f-484">Центр поставщика OIDC.</span><span class="sxs-lookup"><span data-stu-id="2a28f-484">The authority of the OIDC provider.</span></span> <span data-ttu-id="2a28f-485">Используется с проверкой подлинности `Individual`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-485">Use with `Individual` authentication.</span></span> <span data-ttu-id="2a28f-486">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-486">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-487">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-487">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2a28f-488">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-488">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-489">Значение по умолчанию — `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-489">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2a28f-490">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-490">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2a28f-491">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-491">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-492">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-492">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2a28f-493">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-493">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-494">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-494">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2a28f-495">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-495">The Client ID for this project.</span></span> <span data-ttu-id="2a28f-496">Используйте для проверки подлинности `IndividualB2C`, `SingleOrg` или `Individual` в автономных сценариях.</span><span class="sxs-lookup"><span data-stu-id="2a28f-496">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="2a28f-497">Значение по умолчанию — `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-497">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2a28f-498">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="2a28f-498">The domain for the directory tenant.</span></span> <span data-ttu-id="2a28f-499">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-499">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-500">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-500">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="2a28f-501">URI идентификатора приложения для серверного API-интерфейса, который требуется вызвать.</span><span class="sxs-lookup"><span data-stu-id="2a28f-501">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="2a28f-502">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-502">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-503">Значение по умолчанию — `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-503">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="2a28f-504">Идентификатор клиента для API, размещенного на сервере.</span><span class="sxs-lookup"><span data-stu-id="2a28f-504">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="2a28f-505">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-506">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-506">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="2a28f-507">Область API, которую клиент должен запросить для подготовки маркера доступа.</span><span class="sxs-lookup"><span data-stu-id="2a28f-507">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="2a28f-508">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-508">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-509">Значение по умолчанию — `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-509">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2a28f-510">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-510">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2a28f-511">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-511">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-512">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-512">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2a28f-513">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2a28f-514">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-514">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2a28f-515">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="2a28f-516">Создает прогрессивное веб-приложение (PWA), поддерживающее установку и автономное использование.</span><span class="sxs-lookup"><span data-stu-id="2a28f-516">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-517">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-517">Turns off HTTPS.</span></span> <span data-ttu-id="2a28f-518">Этот параметр применяется, только если `Individual`, `IndividualB2C` или `SingleOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-518">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2a28f-519">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2a28f-519">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2a28f-520">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-520">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="2a28f-521">URL-адрес API для вызова из веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-521">URL of the API to call from the web app.</span></span> <span data-ttu-id="2a28f-522">Применяется только при проверке подлинности `SingleOrg` или `IndividualB2C` без указания узла ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2a28f-522">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="2a28f-523">Значение по умолчанию — `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-523">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="2a28f-524">Указывает, вызывает ли веб-приложение Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2a28f-524">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="2a28f-525">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-525">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="2a28f-526">Области для запроса вызова API из веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-526">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="2a28f-527">Применяется только при проверке подлинности `SingleOrg` или `IndividualB2C` без указания узла ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2a28f-527">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="2a28f-528">Значение по умолчанию — `user.read`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-528">The default is `user.read`.</span></span>

<span data-ttu-id="2a28f-529">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-529">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="2a28f-530">web</span><span class="sxs-lookup"><span data-stu-id="2a28f-530">web</span></span>

- <span data-ttu-id="2a28f-531">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-531">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="2a28f-532">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2a28f-533">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-534">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="2a28f-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2a28f-535">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-536">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-536">SDK version</span></span> | <span data-ttu-id="2a28f-537">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-538">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-538">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-539">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-539">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-540">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-540">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2a28f-541">2.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-541">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="2a28f-542">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-543">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-543">Turns off HTTPS.</span></span>

<span data-ttu-id="2a28f-544">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-544">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="2a28f-545">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="2a28f-545">mvc, webapp</span></span>

- <span data-ttu-id="2a28f-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="2a28f-547">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-547">The type of authentication to use.</span></span> <span data-ttu-id="2a28f-548">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2a28f-548">The possible values are:</span></span>

  - <span data-ttu-id="2a28f-549">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a28f-549">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2a28f-550">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-550">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="2a28f-551">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="2a28f-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2a28f-552">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="2a28f-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="2a28f-553">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a28f-553">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="2a28f-554">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="2a28f-554">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-555">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-555">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2a28f-556">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-556">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-557">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-557">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2a28f-558">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-558">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2a28f-559">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-559">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="2a28f-560">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-560">The reset password policy ID for this project.</span></span> <span data-ttu-id="2a28f-561">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-561">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="2a28f-562">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-562">The edit profile policy ID for this project.</span></span> <span data-ttu-id="2a28f-563">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-563">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-564">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-564">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2a28f-565">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-565">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="2a28f-566">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-566">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2a28f-567">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-567">The Client ID for this project.</span></span> <span data-ttu-id="2a28f-568">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-568">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="2a28f-569">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-569">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2a28f-570">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="2a28f-570">The domain for the directory tenant.</span></span> <span data-ttu-id="2a28f-571">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-571">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-572">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-572">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2a28f-573">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-573">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2a28f-574">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-574">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-575">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-575">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="2a28f-576">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-576">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="2a28f-577">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-577">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-578">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-578">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2a28f-579">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-579">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2a28f-580">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-580">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2a28f-581">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-581">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-582">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-582">Turns off HTTPS.</span></span> <span data-ttu-id="2a28f-583">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="2a28f-583">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2a28f-584">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2a28f-584">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2a28f-585">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-585">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2a28f-586">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-586">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-587">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-587">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="2a28f-588">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-588">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-589">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-589">SDK version</span></span> | <span data-ttu-id="2a28f-590">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-590">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-591">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-591">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-592">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-592">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-593">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-593">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="2a28f-594">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-594">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="2a28f-595">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="2a28f-595">Includes BrowserLink in the project.</span></span> <span data-ttu-id="2a28f-596">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="2a28f-596">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="2a28f-597">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="2a28f-597">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="2a28f-598">Параметр доступен начиная с пакета SDK для .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="2a28f-598">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="2a28f-599">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-599">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="2a28f-600">angular, react</span><span class="sxs-lookup"><span data-stu-id="2a28f-600">angular, react</span></span>

- <span data-ttu-id="2a28f-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="2a28f-602">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-602">The type of authentication to use.</span></span> <span data-ttu-id="2a28f-603">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-603">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="2a28f-604">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2a28f-604">The possible values are:</span></span>

  - <span data-ttu-id="2a28f-605">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a28f-605">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2a28f-606">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-606">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2a28f-607">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-607">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2a28f-608">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-608">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-609">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-609">Turns off HTTPS.</span></span> <span data-ttu-id="2a28f-610">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-610">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2a28f-611">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2a28f-611">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2a28f-612">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-612">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-613">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-613">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2a28f-614">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-614">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-615">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="2a28f-615">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2a28f-616">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-616">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-617">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-617">SDK version</span></span> | <span data-ttu-id="2a28f-618">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-618">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-619">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-619">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-620">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-620">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-621">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-621">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2a28f-622">2.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-622">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="2a28f-623">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-623">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="2a28f-624">reactredux</span><span class="sxs-lookup"><span data-stu-id="2a28f-624">reactredux</span></span>

- <span data-ttu-id="2a28f-625">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-625">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="2a28f-626">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-626">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2a28f-627">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-627">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-628">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="2a28f-628">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2a28f-629">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-629">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-630">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-630">SDK version</span></span> | <span data-ttu-id="2a28f-631">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-631">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-632">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-632">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-633">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-633">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-634">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-634">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2a28f-635">2.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-635">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="2a28f-636">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-636">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-637">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-637">Turns off HTTPS.</span></span>

<span data-ttu-id="2a28f-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-638">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="2a28f-639">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="2a28f-639">razorclasslib</span></span>

- <span data-ttu-id="2a28f-640">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-640">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="2a28f-641">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-641">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="2a28f-642">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="2a28f-642">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="2a28f-643">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a28f-643">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="2a28f-644">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-644">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="2a28f-645">webapi</span><span class="sxs-lookup"><span data-stu-id="2a28f-645">webapi</span></span>

- <span data-ttu-id="2a28f-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="2a28f-647">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-647">The type of authentication to use.</span></span> <span data-ttu-id="2a28f-648">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2a28f-648">The possible values are:</span></span>

  - <span data-ttu-id="2a28f-649">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a28f-649">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2a28f-650">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="2a28f-650">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2a28f-651">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="2a28f-651">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="2a28f-652">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="2a28f-652">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-653">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-653">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2a28f-654">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-654">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2a28f-655">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-655">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2a28f-656">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-656">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2a28f-657">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-657">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2a28f-658">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-658">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2a28f-659">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-659">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-660">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-660">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2a28f-661">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2a28f-661">The Client ID for this project.</span></span> <span data-ttu-id="2a28f-662">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-662">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-663">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-663">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2a28f-664">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="2a28f-664">The domain for the directory tenant.</span></span> <span data-ttu-id="2a28f-665">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-665">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-666">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-666">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2a28f-667">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="2a28f-667">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2a28f-668">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-668">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2a28f-669">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-669">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2a28f-670">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="2a28f-670">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2a28f-671">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-671">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2a28f-672">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a28f-672">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="2a28f-673">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2a28f-673">Turns off HTTPS.</span></span> <span data-ttu-id="2a28f-674">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-674">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="2a28f-675">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a28f-675">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2a28f-676">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2a28f-676">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2a28f-677">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="2a28f-677">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2a28f-678">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2a28f-678">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2a28f-679">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="2a28f-679">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2a28f-680">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="2a28f-680">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2a28f-681">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2a28f-681">SDK version</span></span> | <span data-ttu-id="2a28f-682">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a28f-682">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2a28f-683">5,0</span><span class="sxs-lookup"><span data-stu-id="2a28f-683">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="2a28f-684">3.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-684">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2a28f-685">3.0</span><span class="sxs-lookup"><span data-stu-id="2a28f-685">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2a28f-686">2.1</span><span class="sxs-lookup"><span data-stu-id="2a28f-686">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="2a28f-687">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="2a28f-687">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="2a28f-688">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2a28f-688">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="2a28f-689">globaljson</span><span class="sxs-lookup"><span data-stu-id="2a28f-689">globaljson</span></span>

- <span data-ttu-id="2a28f-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="2a28f-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="2a28f-691">Задает версию пакета SDK для .NET, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="2a28f-691">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="2a28f-692">Примеры</span><span class="sxs-lookup"><span data-stu-id="2a28f-692">Examples</span></span>

- <span data-ttu-id="2a28f-693">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="2a28f-693">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="2a28f-694">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="2a28f-694">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="2a28f-695">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="2a28f-695">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="2a28f-696">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="2a28f-696">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="2a28f-697">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="2a28f-697">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="2a28f-698">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="2a28f-698">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="2a28f-699">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="2a28f-699">List all templates matching the *we* substring.</span></span> <span data-ttu-id="2a28f-700">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="2a28f-700">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="2a28f-701">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="2a28f-701">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="2a28f-702">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="2a28f-702">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="2a28f-703">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="2a28f-703">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="2a28f-704">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="2a28f-704">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="2a28f-705">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="2a28f-705">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="2a28f-706">См. также</span><span class="sxs-lookup"><span data-stu-id="2a28f-706">See also</span></span>

- [<span data-ttu-id="2a28f-707">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="2a28f-707">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="2a28f-708">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="2a28f-708">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="2a28f-709">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="2a28f-709">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="2a28f-710">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="2a28f-710">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
