---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 04/10/2020
ms.openlocfilehash: 4ad0d7e54f93582237ed9457b562957018916d36
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463614"
---
# <a name="dotnet-new"></a><span data-ttu-id="1dfc0-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1dfc0-103">dotnet new</span></span>

<span data-ttu-id="1dfc0-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="1dfc0-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1dfc0-105">name</span><span class="sxs-lookup"><span data-stu-id="1dfc0-105">Name</span></span>

<span data-ttu-id="1dfc0-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1dfc0-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1dfc0-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="1dfc0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1dfc0-108">Description</span></span>

<span data-ttu-id="1dfc0-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="1dfc0-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="1dfc0-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1dfc0-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="1dfc0-112">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="1dfc0-113">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="1dfc0-114">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="1dfc0-115">Вы можете запустить `dotnet new --list`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="1dfc0-116">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="1dfc0-117">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="1dfc0-118">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="1dfc0-118">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="1dfc0-119">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-119">If there's a newer version of the template available.</span></span> <span data-ttu-id="1dfc0-120">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="1dfc0-121">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-121">The command contains a default list of templates.</span></span> <span data-ttu-id="1dfc0-122">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="1dfc0-123">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="1dfc0-124">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="1dfc0-125">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="1dfc0-126">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="1dfc0-126">Templates</span></span>                                    | <span data-ttu-id="1dfc0-127">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="1dfc0-127">Short name</span></span>                      | <span data-ttu-id="1dfc0-128">Язык</span><span class="sxs-lookup"><span data-stu-id="1dfc0-128">Language</span></span>     | <span data-ttu-id="1dfc0-129">Tags</span><span class="sxs-lookup"><span data-stu-id="1dfc0-129">Tags</span></span>                                  | <span data-ttu-id="1dfc0-130">Введенный</span><span class="sxs-lookup"><span data-stu-id="1dfc0-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="1dfc0-131">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="1dfc0-131">Console Application</span></span>                          | [<span data-ttu-id="1dfc0-132">Консоль</span><span class="sxs-lookup"><span data-stu-id="1dfc0-132">console</span></span>](#console)             | <span data-ttu-id="1dfc0-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1dfc0-133">[C#], F#, VB</span></span> | <span data-ttu-id="1dfc0-134">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="1dfc0-134">Common/Console</span></span>                        | <span data-ttu-id="1dfc0-135">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-135">1.0</span></span>        |
| <span data-ttu-id="1dfc0-136">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="1dfc0-136">Class library</span></span>                                | [<span data-ttu-id="1dfc0-137">classlib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-137">classlib</span></span>](#classlib)           | <span data-ttu-id="1dfc0-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1dfc0-138">[C#], F#, VB</span></span> | <span data-ttu-id="1dfc0-139">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="1dfc0-139">Common/Library</span></span>                        | <span data-ttu-id="1dfc0-140">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-140">1.0</span></span>        |
| <span data-ttu-id="1dfc0-141">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-141">WPF Application</span></span>                              | [<span data-ttu-id="1dfc0-142">wpf</span><span class="sxs-lookup"><span data-stu-id="1dfc0-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="1dfc0-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-143">[C#]</span></span>         | <span data-ttu-id="1dfc0-144">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-144">Common/WPF</span></span>                            | <span data-ttu-id="1dfc0-145">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-145">3.0</span></span>        |
| <span data-ttu-id="1dfc0-146">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-146">WPF Class library</span></span>                            | [<span data-ttu-id="1dfc0-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="1dfc0-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-148">[C#]</span></span>         | <span data-ttu-id="1dfc0-149">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-149">Common/WPF</span></span>                            | <span data-ttu-id="1dfc0-150">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-150">3.0</span></span>        |
| <span data-ttu-id="1dfc0-151">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="1dfc0-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="1dfc0-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-153">[C#]</span></span>         | <span data-ttu-id="1dfc0-154">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-154">Common/WPF</span></span>                            | <span data-ttu-id="1dfc0-155">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-155">3.0</span></span>        |
| <span data-ttu-id="1dfc0-156">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="1dfc0-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="1dfc0-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-158">[C#]</span></span>         | <span data-ttu-id="1dfc0-159">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="1dfc0-159">Common/WPF</span></span>                            | <span data-ttu-id="1dfc0-160">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-160">3.0</span></span>        |
| <span data-ttu-id="1dfc0-161">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1dfc0-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="1dfc0-162">winforms</span><span class="sxs-lookup"><span data-stu-id="1dfc0-162">winforms</span></span>](#winforms)           | <span data-ttu-id="1dfc0-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-163">[C#]</span></span>         | <span data-ttu-id="1dfc0-164">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1dfc0-164">Common/WinForms</span></span>                       | <span data-ttu-id="1dfc0-165">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-165">3.0</span></span>        |
| <span data-ttu-id="1dfc0-166">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1dfc0-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="1dfc0-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="1dfc0-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-168">[C#]</span></span>         | <span data-ttu-id="1dfc0-169">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1dfc0-169">Common/WinForms</span></span>                       | <span data-ttu-id="1dfc0-170">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-170">3.0</span></span>        |
| <span data-ttu-id="1dfc0-171">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="1dfc0-171">Worker Service</span></span>                               | [<span data-ttu-id="1dfc0-172">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="1dfc0-172">worker</span></span>](#web-others)           | <span data-ttu-id="1dfc0-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-173">[C#]</span></span>         | <span data-ttu-id="1dfc0-174">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="1dfc0-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="1dfc0-175">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-175">3.0</span></span>        |
| <span data-ttu-id="1dfc0-176">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="1dfc0-176">Unit Test Project</span></span>                            | [<span data-ttu-id="1dfc0-177">mstest</span><span class="sxs-lookup"><span data-stu-id="1dfc0-177">mstest</span></span>](#test)                 | <span data-ttu-id="1dfc0-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1dfc0-178">[C#], F#, VB</span></span> | <span data-ttu-id="1dfc0-179">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="1dfc0-179">Test/MSTest</span></span>                           | <span data-ttu-id="1dfc0-180">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-180">1.0</span></span>        |
| <span data-ttu-id="1dfc0-181">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="1dfc0-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="1dfc0-182">nunit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="1dfc0-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1dfc0-183">[C#], F#, VB</span></span> | <span data-ttu-id="1dfc0-184">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-184">Test/NUnit</span></span>                            | <span data-ttu-id="1dfc0-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="1dfc0-185">2.1.400</span></span>    |
| <span data-ttu-id="1dfc0-186">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="1dfc0-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="1dfc0-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1dfc0-187">[C#], F#, VB</span></span> | <span data-ttu-id="1dfc0-188">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-188">Test/NUnit</span></span>                            | <span data-ttu-id="1dfc0-189">2.2</span><span class="sxs-lookup"><span data-stu-id="1dfc0-189">2.2</span></span>        |
| <span data-ttu-id="1dfc0-190">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="1dfc0-191">xunit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-191">xunit</span></span>](#test)                  | <span data-ttu-id="1dfc0-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1dfc0-192">[C#], F#, VB</span></span> | <span data-ttu-id="1dfc0-193">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-193">Test/xUnit</span></span>                            | <span data-ttu-id="1dfc0-194">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-194">1.0</span></span>        |
| <span data-ttu-id="1dfc0-195">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="1dfc0-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-196">[C#]</span></span>         | <span data-ttu-id="1dfc0-197">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1dfc0-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="1dfc0-198">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-198">3.0</span></span>        |
| <span data-ttu-id="1dfc0-199">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-199">Razor Page</span></span>                                   | [<span data-ttu-id="1dfc0-200">page</span><span class="sxs-lookup"><span data-stu-id="1dfc0-200">page</span></span>](#page)                   | <span data-ttu-id="1dfc0-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-201">[C#]</span></span>         | <span data-ttu-id="1dfc0-202">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1dfc0-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="1dfc0-203">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-203">2.0</span></span>        |
| <span data-ttu-id="1dfc0-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="1dfc0-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="1dfc0-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="1dfc0-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="1dfc0-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-206">[C#]</span></span>         | <span data-ttu-id="1dfc0-207">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1dfc0-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="1dfc0-208">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-208">2.0</span></span>        |
| <span data-ttu-id="1dfc0-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="1dfc0-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="1dfc0-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-210">[C#]</span></span>         | <span data-ttu-id="1dfc0-211">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1dfc0-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="1dfc0-212">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-212">2.0</span></span>        |
| <span data-ttu-id="1dfc0-213">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-213">Blazor Server App</span></span>                            | [<span data-ttu-id="1dfc0-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="1dfc0-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="1dfc0-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-215">[C#]</span></span>         | <span data-ttu-id="1dfc0-216">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-216">Web/Blazor</span></span>                            | <span data-ttu-id="1dfc0-217">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-217">3.0</span></span>        |
| <span data-ttu-id="1dfc0-218">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1dfc0-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="1dfc0-219">web</span><span class="sxs-lookup"><span data-stu-id="1dfc0-219">web</span></span>](#web)                     | <span data-ttu-id="1dfc0-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1dfc0-220">[C#], F#</span></span>     | <span data-ttu-id="1dfc0-221">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="1dfc0-221">Web/Empty</span></span>                             | <span data-ttu-id="1dfc0-222">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-222">1.0</span></span>        |
| <span data-ttu-id="1dfc0-223">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="1dfc0-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="1dfc0-224">mvc</span><span class="sxs-lookup"><span data-stu-id="1dfc0-224">mvc</span></span>](#web-options)             | <span data-ttu-id="1dfc0-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1dfc0-225">[C#], F#</span></span>     | <span data-ttu-id="1dfc0-226">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="1dfc0-226">Web/MVC</span></span>                               | <span data-ttu-id="1dfc0-227">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-227">1.0</span></span>        |
| <span data-ttu-id="1dfc0-228">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1dfc0-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="1dfc0-229">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="1dfc0-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-230">[C#]</span></span>         | <span data-ttu-id="1dfc0-231">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="1dfc0-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="1dfc0-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="1dfc0-233">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="1dfc0-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="1dfc0-234">angular</span><span class="sxs-lookup"><span data-stu-id="1dfc0-234">angular</span></span>](#spa)                 | <span data-ttu-id="1dfc0-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-235">[C#]</span></span>         | <span data-ttu-id="1dfc0-236">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="1dfc0-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1dfc0-237">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-237">2.0</span></span>        |
| <span data-ttu-id="1dfc0-238">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="1dfc0-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="1dfc0-239">react</span><span class="sxs-lookup"><span data-stu-id="1dfc0-239">react</span></span>](#spa)                   | <span data-ttu-id="1dfc0-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-240">[C#]</span></span>         | <span data-ttu-id="1dfc0-241">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="1dfc0-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1dfc0-242">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-242">2.0</span></span>        |
| <span data-ttu-id="1dfc0-243">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="1dfc0-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="1dfc0-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="1dfc0-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="1dfc0-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-245">[C#]</span></span>         | <span data-ttu-id="1dfc0-246">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="1dfc0-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1dfc0-247">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-247">2.0</span></span>        |
| <span data-ttu-id="1dfc0-248">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-248">Razor Class Library</span></span>                          | [<span data-ttu-id="1dfc0-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="1dfc0-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-250">[C#]</span></span>         | <span data-ttu-id="1dfc0-251">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="1dfc0-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="1dfc0-252">2.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-252">2.1</span></span>        |
| <span data-ttu-id="1dfc0-253">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1dfc0-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="1dfc0-254">webapi</span><span class="sxs-lookup"><span data-stu-id="1dfc0-254">webapi</span></span>](#webapi)               | <span data-ttu-id="1dfc0-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1dfc0-255">[C#], F#</span></span>     | <span data-ttu-id="1dfc0-256">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="1dfc0-256">Web/WebAPI</span></span>                            | <span data-ttu-id="1dfc0-257">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-257">1.0</span></span>        |
| <span data-ttu-id="1dfc0-258">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="1dfc0-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="1dfc0-259">grpc</span><span class="sxs-lookup"><span data-stu-id="1dfc0-259">grpc</span></span>](#web-others)             | <span data-ttu-id="1dfc0-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="1dfc0-260">[C#]</span></span>         | <span data-ttu-id="1dfc0-261">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="1dfc0-261">Web/gRPC</span></span>                              | <span data-ttu-id="1dfc0-262">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-262">3.0</span></span>        |
| <span data-ttu-id="1dfc0-263">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="1dfc0-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="1dfc0-264">proto</span><span class="sxs-lookup"><span data-stu-id="1dfc0-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="1dfc0-265">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="1dfc0-265">Web/gRPC</span></span>                              | <span data-ttu-id="1dfc0-266">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-266">3.0</span></span>        |
| <span data-ttu-id="1dfc0-267">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="1dfc0-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="1dfc0-268">Config</span><span class="sxs-lookup"><span data-stu-id="1dfc0-268">Config</span></span>                                | <span data-ttu-id="1dfc0-269">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-269">3.0</span></span>        |
| <span data-ttu-id="1dfc0-270">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="1dfc0-270">global.json file</span></span>                             | [<span data-ttu-id="1dfc0-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="1dfc0-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="1dfc0-272">Config</span><span class="sxs-lookup"><span data-stu-id="1dfc0-272">Config</span></span>                                | <span data-ttu-id="1dfc0-273">2.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-273">2.0</span></span>        |
| <span data-ttu-id="1dfc0-274">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="1dfc0-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="1dfc0-275">Config</span><span class="sxs-lookup"><span data-stu-id="1dfc0-275">Config</span></span>                                | <span data-ttu-id="1dfc0-276">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-276">1.0</span></span>        |
| <span data-ttu-id="1dfc0-277">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="1dfc0-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="1dfc0-278">Config</span><span class="sxs-lookup"><span data-stu-id="1dfc0-278">Config</span></span>                                | <span data-ttu-id="1dfc0-279">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-279">3.0</span></span>        |
| <span data-ttu-id="1dfc0-280">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="1dfc0-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="1dfc0-281">Config</span><span class="sxs-lookup"><span data-stu-id="1dfc0-281">Config</span></span>                                | <span data-ttu-id="1dfc0-282">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-282">1.0</span></span>        |
| <span data-ttu-id="1dfc0-283">Файл решения</span><span class="sxs-lookup"><span data-stu-id="1dfc0-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="1dfc0-284">Решение</span><span class="sxs-lookup"><span data-stu-id="1dfc0-284">Solution</span></span>                              | <span data-ttu-id="1dfc0-285">1.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="1dfc0-286">Параметры</span><span class="sxs-lookup"><span data-stu-id="1dfc0-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="1dfc0-287">Отображает сводку того, что произойдет, если выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="1dfc0-288">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="1dfc0-289">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="1dfc0-290">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1dfc0-291">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-291">Prints out help for the command.</span></span> <span data-ttu-id="1dfc0-292">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="1dfc0-293">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="1dfc0-294">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1dfc0-295">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="1dfc0-296">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="1dfc0-297">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="1dfc0-298">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="1dfc0-299">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="1dfc0-300">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="1dfc0-301">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="1dfc0-302">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-302">The language of the template to create.</span></span> <span data-ttu-id="1dfc0-303">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="1dfc0-304">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1dfc0-305">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="1dfc0-306">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="1dfc0-307">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="1dfc0-308">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-308">The name for the created output.</span></span> <span data-ttu-id="1dfc0-309">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="1dfc0-310">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="1dfc0-311">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1dfc0-312">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-312">Location to place the generated output.</span></span> <span data-ttu-id="1dfc0-313">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-313">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="1dfc0-314">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-314">Filters templates based on available types.</span></span> <span data-ttu-id="1dfc0-315">Предопределенные значения: `project`, `item` или `other`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-315">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="1dfc0-316">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1dfc0-317">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="1dfc0-318">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="1dfc0-319">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1dfc0-320">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="1dfc0-321">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="1dfc0-322">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="1dfc0-323">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="1dfc0-324">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="1dfc0-325">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="1dfc0-326">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="1dfc0-327">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="1dfc0-327">Template options</span></span>

<span data-ttu-id="1dfc0-328">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-328">Each project template may have additional options available.</span></span> <span data-ttu-id="1dfc0-329">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="1dfc0-330">console</span><span class="sxs-lookup"><span data-stu-id="1dfc0-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-331">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-332">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1dfc0-333">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-334">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-334">SDK version</span></span> | <span data-ttu-id="1dfc0-335">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-336">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-337">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1dfc0-338">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1dfc0-339">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="1dfc0-340">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-340">Not supported for F#.</span></span> <span data-ttu-id="1dfc0-341">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1dfc0-342">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-343">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="1dfc0-344">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="1dfc0-345">classlib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-346">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-347">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="1dfc0-348">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1dfc0-349">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1dfc0-350">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="1dfc0-351">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-351">Not supported for F#.</span></span> <span data-ttu-id="1dfc0-352">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1dfc0-353">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-354">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="1dfc0-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-356">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-357">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="1dfc0-358">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1dfc0-359">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1dfc0-360">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="1dfc0-361">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-362">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="1dfc0-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1dfc0-364">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1dfc0-365">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="1dfc0-366">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-367">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="1dfc0-368">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="1dfc0-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-369">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-370">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="1dfc0-371">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-372">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-373">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="1dfc0-374">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-375">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-376">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1dfc0-377">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-378">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-378">SDK version</span></span> | <span data-ttu-id="1dfc0-379">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-380">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-381">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="1dfc0-382">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-383">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="1dfc0-384">nunit</span><span class="sxs-lookup"><span data-stu-id="1dfc0-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-385">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="1dfc0-386">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-387">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-387">SDK version</span></span> | <span data-ttu-id="1dfc0-388">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-389">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-390">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1dfc0-391">2.2</span><span class="sxs-lookup"><span data-stu-id="1dfc0-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="1dfc0-392">2.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="1dfc0-393">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-394">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="1dfc0-395">страница</span><span class="sxs-lookup"><span data-stu-id="1dfc0-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="1dfc0-396">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-396">Namespace for the generated code.</span></span> <span data-ttu-id="1dfc0-397">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="1dfc0-398">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-398">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="1dfc0-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="1dfc0-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="1dfc0-400">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-400">Namespace for the generated code.</span></span> <span data-ttu-id="1dfc0-401">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="1dfc0-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="1dfc0-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1dfc0-403">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-403">The type of authentication to use.</span></span> <span data-ttu-id="1dfc0-404">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-404">The possible values are:</span></span>

  - <span data-ttu-id="1dfc0-405">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1dfc0-406">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="1dfc0-407">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1dfc0-408">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1dfc0-409">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="1dfc0-410">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1dfc0-411">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1dfc0-412">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-413">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1dfc0-414">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1dfc0-415">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="1dfc0-416">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="1dfc0-417">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="1dfc0-418">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="1dfc0-419">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1dfc0-420">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1dfc0-421">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1dfc0-422">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1dfc0-423">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-423">The Client ID for this project.</span></span> <span data-ttu-id="1dfc0-424">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1dfc0-425">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1dfc0-426">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-426">The domain for the directory tenant.</span></span> <span data-ttu-id="1dfc0-427">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-428">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1dfc0-429">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1dfc0-430">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1dfc0-431">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="1dfc0-432">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1dfc0-433">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-434">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1dfc0-435">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1dfc0-436">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-437">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1dfc0-438">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-438">Turns off HTTPS.</span></span> <span data-ttu-id="1dfc0-439">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1dfc0-440">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1dfc0-441">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-442">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="1dfc0-443">web</span><span class="sxs-lookup"><span data-stu-id="1dfc0-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-444">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-445">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-446">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1dfc0-447">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-448">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-448">SDK version</span></span> | <span data-ttu-id="1dfc0-449">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-450">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-451">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1dfc0-452">2.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="1dfc0-453">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1dfc0-454">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-454">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="1dfc0-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="1dfc0-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1dfc0-456">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-456">The type of authentication to use.</span></span> <span data-ttu-id="1dfc0-457">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-457">The possible values are:</span></span>

  - <span data-ttu-id="1dfc0-458">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1dfc0-459">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="1dfc0-460">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1dfc0-461">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1dfc0-462">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="1dfc0-463">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1dfc0-464">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1dfc0-465">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-466">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1dfc0-467">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1dfc0-468">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="1dfc0-469">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="1dfc0-470">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="1dfc0-471">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="1dfc0-472">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1dfc0-473">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1dfc0-474">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1dfc0-475">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1dfc0-476">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-476">The Client ID for this project.</span></span> <span data-ttu-id="1dfc0-477">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1dfc0-478">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1dfc0-479">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-479">The domain for the directory tenant.</span></span> <span data-ttu-id="1dfc0-480">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-481">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1dfc0-482">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1dfc0-483">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1dfc0-484">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="1dfc0-485">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1dfc0-486">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-487">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1dfc0-488">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1dfc0-489">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-490">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1dfc0-491">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-491">Turns off HTTPS.</span></span> <span data-ttu-id="1dfc0-492">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1dfc0-493">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1dfc0-494">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-495">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-496">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1dfc0-497">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-498">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-498">SDK version</span></span> | <span data-ttu-id="1dfc0-499">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-500">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-501">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="1dfc0-502">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="1dfc0-503">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="1dfc0-504">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="1dfc0-505">Определяет, настроен ли проект для использования [компиляции среды выполнения Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) в отладочных сборках.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-505">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="1dfc0-506">Параметр доступен, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-506">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="1dfc0-507">angular, react</span><span class="sxs-lookup"><span data-stu-id="1dfc0-507">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1dfc0-508">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-508">The type of authentication to use.</span></span> <span data-ttu-id="1dfc0-509">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-509">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="1dfc0-510">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-510">The possible values are:</span></span>

  - <span data-ttu-id="1dfc0-511">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-511">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1dfc0-512">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-512">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-513">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-514">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-514">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1dfc0-515">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-515">Turns off HTTPS.</span></span> <span data-ttu-id="1dfc0-516">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-516">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1dfc0-517">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1dfc0-518">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-519">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-519">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-520">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-521">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-521">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1dfc0-522">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-523">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-523">SDK version</span></span> | <span data-ttu-id="1dfc0-524">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-525">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-526">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-526">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1dfc0-527">2.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-527">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="1dfc0-528">reactredux</span><span class="sxs-lookup"><span data-stu-id="1dfc0-528">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-529">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-529">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-530">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-530">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-531">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-531">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1dfc0-532">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-532">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-533">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-533">SDK version</span></span> | <span data-ttu-id="1dfc0-534">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-534">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-535">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-535">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-536">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-536">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1dfc0-537">2.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-537">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="1dfc0-538">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-538">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1dfc0-539">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-539">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="1dfc0-540">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1dfc0-540">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="1dfc0-541">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="1dfc0-542">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-542">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="1dfc0-543">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-543">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="1dfc0-544">webapi</span><span class="sxs-lookup"><span data-stu-id="1dfc0-544">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1dfc0-545">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-545">The type of authentication to use.</span></span> <span data-ttu-id="1dfc0-546">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-546">The possible values are:</span></span>

  - <span data-ttu-id="1dfc0-547">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-547">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1dfc0-548">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1dfc0-549">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1dfc0-550">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-550">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1dfc0-551">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-551">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1dfc0-552">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-552">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1dfc0-553">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-553">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1dfc0-554">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-554">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1dfc0-555">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-555">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1dfc0-556">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-556">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1dfc0-557">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-557">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1dfc0-558">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-558">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1dfc0-559">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-559">The Client ID for this project.</span></span> <span data-ttu-id="1dfc0-560">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-560">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1dfc0-561">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-561">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1dfc0-562">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-562">The domain for the directory tenant.</span></span> <span data-ttu-id="1dfc0-563">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1dfc0-564">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-564">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1dfc0-565">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-565">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1dfc0-566">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-566">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1dfc0-567">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-567">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1dfc0-568">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-568">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1dfc0-569">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-569">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1dfc0-570">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-570">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1dfc0-571">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-571">Turns off HTTPS.</span></span> <span data-ttu-id="1dfc0-572">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-572">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="1dfc0-573">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-573">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1dfc0-574">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-574">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1dfc0-575">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-575">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1dfc0-576">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1dfc0-576">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1dfc0-577">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-577">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1dfc0-578">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-578">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1dfc0-579">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="1dfc0-579">SDK version</span></span> | <span data-ttu-id="1dfc0-580">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1dfc0-580">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1dfc0-581">3.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-581">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1dfc0-582">3.0</span><span class="sxs-lookup"><span data-stu-id="1dfc0-582">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1dfc0-583">2.1</span><span class="sxs-lookup"><span data-stu-id="1dfc0-583">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="1dfc0-584">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-584">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="1dfc0-585">globaljson</span><span class="sxs-lookup"><span data-stu-id="1dfc0-585">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="1dfc0-586">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-586">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="1dfc0-587">Примеры</span><span class="sxs-lookup"><span data-stu-id="1dfc0-587">Examples</span></span>

- <span data-ttu-id="1dfc0-588">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-588">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="1dfc0-589">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-589">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="1dfc0-590">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-590">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="1dfc0-591">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-591">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="1dfc0-592">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-592">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="1dfc0-593">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="1dfc0-593">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="1dfc0-594">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-594">List all templates matching the *we* substring.</span></span> <span data-ttu-id="1dfc0-595">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-595">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="1dfc0-596">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-596">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="1dfc0-597">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="1dfc0-597">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="1dfc0-598">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-598">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="1dfc0-599">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-599">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="1dfc0-600">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="1dfc0-600">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="1dfc0-601">См. также</span><span class="sxs-lookup"><span data-stu-id="1dfc0-601">See also</span></span>

- [<span data-ttu-id="1dfc0-602">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="1dfc0-602">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="1dfc0-603">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="1dfc0-603">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="1dfc0-604">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="1dfc0-604">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="1dfc0-605">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="1dfc0-605">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
