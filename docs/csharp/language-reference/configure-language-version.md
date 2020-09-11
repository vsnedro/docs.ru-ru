---
title: Управление версиями языка C# — руководство по C#
description: Дополнительные сведения о том, как версия языка C# определяется на основе вашего проекта и какие причины лежат в основе этого решения. Сведения о ручном переопределении значения по умолчанию.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: 327a98da37b97830ac7f752a3621a92d8cb161e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495464"
---
# <a name="c-language-versioning"></a><span data-ttu-id="72c16-104">Управление версиями языка C#</span><span class="sxs-lookup"><span data-stu-id="72c16-104">C# language versioning</span></span>

<span data-ttu-id="72c16-105">Компилятор C# последней версии определяет версию языка по умолчанию на основе целевой платформы или платформ проекта.</span><span class="sxs-lookup"><span data-stu-id="72c16-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="72c16-106">Visual Studio не предоставляет пользовательский интерфейс для изменения этого значения, но его можно изменить, отредактировав файл *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="72c16-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="72c16-107">Выбор значения по умолчанию гарантирует, что вы используете последнюю версию языка, совместимую с вашей целевой платформой.</span><span class="sxs-lookup"><span data-stu-id="72c16-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="72c16-108">Вы получите преимущество в виде доступа к последним функциям языка, совместимым с целевым объектом проекта.</span><span class="sxs-lookup"><span data-stu-id="72c16-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="72c16-109">Этот вариант по умолчанию также гарантирует, что вы не будете использовать язык, который требует такие типы или поведение во время выполнения, которые недоступны в целевой платформе.</span><span class="sxs-lookup"><span data-stu-id="72c16-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="72c16-110">Выбор более новой версии языка, чем значение по умолчанию, может усложнить диагностику ошибок во время компиляции и выполнения.</span><span class="sxs-lookup"><span data-stu-id="72c16-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="72c16-111">Приведенные в этой статье правила относятся к компилятору, поставляемому с Visual Studio 2019, или к пакету SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="72c16-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET SDK.</span></span> <span data-ttu-id="72c16-112">Компиляторы C#, которые являются частью установки Visual Studio 2017 или более ранних версий пакета SDK для .NET Core предназначены для C# 7.0 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72c16-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="72c16-113">C# 8.0 поддерживается только в .NET Core 3.x и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="72c16-113">C# 8.0 is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="72c16-114">Для многих новых функций нужны функции среды выполнения и библиотеки, появившиеся в .NET Core 3. x:</span><span class="sxs-lookup"><span data-stu-id="72c16-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="72c16-115">[Для реализации интерфейса по умолчанию](../whats-new/csharp-8.md#default-interface-methods) требуются новые функции в среде CLR .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="72c16-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="72c16-116">Для [асинхронных потоков](../whats-new/csharp-8.md#asynchronous-streams) требуются новые типы <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> и <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72c16-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="72c16-117">Для [индексов и диапазонов](../whats-new/csharp-8.md#indices-and-ranges) требуются новые типы <xref:System.Index?displayProperty=nameWithType> и <xref:System.Range?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72c16-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="72c16-118">[Ссылочные типы, допускающие значение NULL](../whats-new/csharp-8.md#nullable-reference-types), используют несколько [атрибутов](attributes/nullable-analysis.md) для предоставления улучшенных предупреждений.</span><span class="sxs-lookup"><span data-stu-id="72c16-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="72c16-119">Эти атрибуты были добавлены в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="72c16-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="72c16-120">Другие целевые платформы не были помечены ни одним из этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="72c16-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="72c16-121">Это означает, что предупреждения, допускающие значение NULL, могут неточно отражать потенциальные проблемы.</span><span class="sxs-lookup"><span data-stu-id="72c16-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

<span data-ttu-id="72c16-122">C# 9.0 поддерживается только в .NET 5 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="72c16-122">C# 9.0 is supported only on .NET 5 and newer versions.</span></span>

## <a name="defaults"></a><span data-ttu-id="72c16-123">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="72c16-123">Defaults</span></span>

<span data-ttu-id="72c16-124">Компилятор определяет значение по умолчанию на основе следующих правил:</span><span class="sxs-lookup"><span data-stu-id="72c16-124">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="72c16-125">Целевая платформа</span><span class="sxs-lookup"><span data-stu-id="72c16-125">Target framework</span></span> | <span data-ttu-id="72c16-126">version</span><span class="sxs-lookup"><span data-stu-id="72c16-126">version</span></span> | <span data-ttu-id="72c16-127">Версия языка C# по умолчанию</span><span class="sxs-lookup"><span data-stu-id="72c16-127">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="72c16-128">.NET</span><span class="sxs-lookup"><span data-stu-id="72c16-128">.NET</span></span>             | <span data-ttu-id="72c16-129">5.x</span><span class="sxs-lookup"><span data-stu-id="72c16-129">5.x</span></span>     | <span data-ttu-id="72c16-130">C# 9.0</span><span class="sxs-lookup"><span data-stu-id="72c16-130">C# 9.0</span></span>                      |
| <span data-ttu-id="72c16-131">.NET Core</span><span class="sxs-lookup"><span data-stu-id="72c16-131">.NET Core</span></span>        | <span data-ttu-id="72c16-132">3.x</span><span class="sxs-lookup"><span data-stu-id="72c16-132">3.x</span></span>     | <span data-ttu-id="72c16-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="72c16-133">C# 8.0</span></span>                      |
| <span data-ttu-id="72c16-134">.NET Core</span><span class="sxs-lookup"><span data-stu-id="72c16-134">.NET Core</span></span>        | <span data-ttu-id="72c16-135">2.x</span><span class="sxs-lookup"><span data-stu-id="72c16-135">2.x</span></span>     | <span data-ttu-id="72c16-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="72c16-136">C# 7.3</span></span>                      |
| <span data-ttu-id="72c16-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="72c16-137">.NET Standard</span></span>    | <span data-ttu-id="72c16-138">2.1</span><span class="sxs-lookup"><span data-stu-id="72c16-138">2.1</span></span>     | <span data-ttu-id="72c16-139">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="72c16-139">C# 8.0</span></span>                      |
| <span data-ttu-id="72c16-140">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="72c16-140">.NET Standard</span></span>    | <span data-ttu-id="72c16-141">2.0</span><span class="sxs-lookup"><span data-stu-id="72c16-141">2.0</span></span>     | <span data-ttu-id="72c16-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="72c16-142">C# 7.3</span></span>                      |
| <span data-ttu-id="72c16-143">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="72c16-143">.NET Standard</span></span>    | <span data-ttu-id="72c16-144">1.x</span><span class="sxs-lookup"><span data-stu-id="72c16-144">1.x</span></span>     | <span data-ttu-id="72c16-145">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="72c16-145">C# 7.3</span></span>                      |
| <span data-ttu-id="72c16-146">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="72c16-146">.NET Framework</span></span>   | <span data-ttu-id="72c16-147">все</span><span class="sxs-lookup"><span data-stu-id="72c16-147">all</span></span>     | <span data-ttu-id="72c16-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="72c16-148">C# 7.3</span></span>                      |

<span data-ttu-id="72c16-149">Если проект предназначен для платформы в предварительной версии с поддержкой соответствующего языка в предварительной версии, будет использоваться язык, поддерживаемый в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="72c16-149">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="72c16-150">Вы можете использовать новейшие возможности в этой предварительной версии в любой среде, не затрагивая проекты, предназначенные для выпущенной версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="72c16-150">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

> [!TIP]
> <span data-ttu-id="72c16-151">Чтобы узнать, какую версию языка вы используете в данный момент, поставьте `#error version` (с учетом регистра) в коде.</span><span class="sxs-lookup"><span data-stu-id="72c16-151">To know what language version you're currently using, put `#error version` (case sensitive) in your code.</span></span> <span data-ttu-id="72c16-152">Это позволяет компилятору создать диагностику CS8304 с сообщением, содержащим сведения об используемой версии компилятора и текущей выбранной версии языка.</span><span class="sxs-lookup"><span data-stu-id="72c16-152">This makes the compiler produce a diagnostic, CS8304, with a message containing the compiler version being used and the current selected language version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="72c16-153">Переопределение значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="72c16-153">Override a default</span></span>

<span data-ttu-id="72c16-154">Если необходимо явно указать версию C#, это можно сделать несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="72c16-154">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="72c16-155">Вручную изменить [файл проекта](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="72c16-155">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="72c16-156">Задать версию языка [для нескольких проектов в подкаталоге](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="72c16-156">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="72c16-157">настройка [параметра компилятора `-langversion`](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="72c16-157">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="72c16-158">Изменение файла проекта</span><span class="sxs-lookup"><span data-stu-id="72c16-158">Edit the project file</span></span>

<span data-ttu-id="72c16-159">Версию языка можно задать в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="72c16-159">You can set the language version in your project file.</span></span> <span data-ttu-id="72c16-160">Например, если доступ к предварительной версии функций должен быть задан явным образом, можно добавить следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="72c16-160">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="72c16-161">Значение `preview` использует последнюю предварительную версию языка C#, которую поддерживает компилятор.</span><span class="sxs-lookup"><span data-stu-id="72c16-161">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="72c16-162">Настройка нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="72c16-162">Configure multiple projects</span></span>

<span data-ttu-id="72c16-163">Чтобы настроить несколько проектов, вы можете создать файл **Directory.Build.props**, содержащий элемент `<LangVersion>`.</span><span class="sxs-lookup"><span data-stu-id="72c16-163">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="72c16-164">Обычно это делается в каталоге решения.</span><span class="sxs-lookup"><span data-stu-id="72c16-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="72c16-165">Добавьте следующий код в файл **Directory.Build.props** в каталоге решения:</span><span class="sxs-lookup"><span data-stu-id="72c16-165">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="72c16-166">Сборки во всех подкаталогах каталога, который содержит этот файл, будут использовать предварительную версию C#.</span><span class="sxs-lookup"><span data-stu-id="72c16-166">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="72c16-167">Дополнительные сведения см. в статье о [настройке сборки](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="72c16-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="72c16-168">Справочник по версиям языка C#</span><span class="sxs-lookup"><span data-stu-id="72c16-168">C# language version reference</span></span>

<span data-ttu-id="72c16-169">В следующей таблице показаны все текущие версии языка C#.</span><span class="sxs-lookup"><span data-stu-id="72c16-169">The following table shows all current C# language versions.</span></span> <span data-ttu-id="72c16-170">Ваш компилятор может не распознавать все значения, если имеет более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="72c16-170">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="72c16-171">При установке .NET Core 3.0 или более поздней версии вы получаете доступ ко всем значениям в таблице.</span><span class="sxs-lookup"><span data-stu-id="72c16-171">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="72c16-172">Откройте [Командную строку разработчика для Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md) и выполните следующую команду, чтобы просмотреть список версий языка, доступных на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="72c16-172">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="72c16-173">В ответ на запрос параметра компиляции [-langversion](compiler-options/langversion-compiler-option.md) такого типа выводится примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="72c16-173">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
