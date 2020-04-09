---
title: Перенос приложения Windows Forms в .NET Core
description: Эта статья описывает, как перенести приложение Windows Forms из .NET Framework в .NET Core для Windows.
author: Thraka
ms.author: adegeo
ms.date: 01/24/2020
ms.openlocfilehash: 80b4bb225d6a6748743d91a4c70e8b09c10cc94b
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635513"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="d079e-103">Процесс переноса классического приложения Windows Forms в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d079e-103">How to port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="d079e-104">Эта статья описывает, как перенести классическое приложение, созданное на основе Windows Forms, из .NET Framework в .NET Core 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d079e-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0 or later.</span></span> <span data-ttu-id="d079e-105">В пакет SDK для .NET Core 3.0 включена поддержка приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d079e-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="d079e-106">Windows Forms — это платформа, которая по-прежнему поддерживается и функционирует только в ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="d079e-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="d079e-107">В этом примере для создания проекта и управления им используется CLI пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="d079e-108">В этой статье применяются различные имена для обозначения типов файлов, используемых для переноса.</span><span class="sxs-lookup"><span data-stu-id="d079e-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="d079e-109">При переносе вашего проекта файлы будут называться иначе, поэтому попытайтесь мысленно сопоставить их с именами из этой таблицы:</span><span class="sxs-lookup"><span data-stu-id="d079e-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="d079e-110">Файл</span><span class="sxs-lookup"><span data-stu-id="d079e-110">File</span></span> | <span data-ttu-id="d079e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d079e-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="d079e-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="d079e-112">**MyApps.sln**</span></span> | <span data-ttu-id="d079e-113">Имя файла решения.</span><span class="sxs-lookup"><span data-stu-id="d079e-113">The name of the solution file.</span></span> |
| <span data-ttu-id="d079e-114">**MyForms.csproj**</span><span class="sxs-lookup"><span data-stu-id="d079e-114">**MyForms.csproj**</span></span> | <span data-ttu-id="d079e-115">Имя проекта Windows Forms в .NET Framework, который нужно перенести.</span><span class="sxs-lookup"><span data-stu-id="d079e-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| <span data-ttu-id="d079e-116">**MyFormsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="d079e-116">**MyFormsCore.csproj**</span></span> | <span data-ttu-id="d079e-117">Имя создаваемого проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="d079e-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="d079e-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="d079e-119">Исполняемый файл приложения Windows Forms в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="d079e-120">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d079e-120">Prerequisites</span></span>

- <span data-ttu-id="d079e-121">[Visual Studio 2019 16.5, предварительная версия 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) или более поздние версии для выполнения задач по конструированию.</span><span class="sxs-lookup"><span data-stu-id="d079e-121">[Visual Studio 2019 16.5 Preview 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) or later for any designer work you want to do.</span></span> <span data-ttu-id="d079e-122">Рекомендуется выполнить обновление до последней [предварительной версии Visual Studio](https://visualstudio.microsoft.com/vs/preview/).</span><span class="sxs-lookup"><span data-stu-id="d079e-122">We recommend to update to the latest [Preview version of Visual Studio](https://visualstudio.microsoft.com/vs/preview/)</span></span>

  <span data-ttu-id="d079e-123">Установите следующие рабочие нагрузки Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="d079e-123">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="d079e-124">Разработка классических приложений .NET</span><span class="sxs-lookup"><span data-stu-id="d079e-124">.NET desktop development</span></span>
  - <span data-ttu-id="d079e-125">Кроссплатформенная разработка .NET Core</span><span class="sxs-lookup"><span data-stu-id="d079e-125">.NET Core cross-platform development</span></span>

- <span data-ttu-id="d079e-126">Функционирующий проект Windows Forms в решении, сборка и запуск которого выполняется без ошибок.</span><span class="sxs-lookup"><span data-stu-id="d079e-126">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="d079e-127">Код проекта написан на C#.</span><span class="sxs-lookup"><span data-stu-id="d079e-127">A project coded in C#.</span></span>

> [!NOTE]
> <span data-ttu-id="d079e-128">Проекты .NET Core 3.0 поддерживаются только в **Visual Studio 2019** или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="d079e-128">.NET Core 3.0 projects are only supported in **Visual Studio 2019** or a later version.</span></span> <span data-ttu-id="d079e-129">Начиная с **Visual Studio 2019 версии 16.5, предварительная версия 1**, также поддерживается конструктор Windows Forms .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-129">Starting with **Visual Studio 2019 version 16.5 Preview 1**, the .NET Core Windows Forms designer is also supported.</span></span>
>
> <span data-ttu-id="d079e-130">Чтобы включить конструктор, последовательно выберите **Сервис** > **Параметры** > **Среда** > **Функции предварительной версии**, а затем выберите параметр **Use the preview Windows Forms designer for .NET Core apps** (Использовать конструктор Windows Forms предварительной версии для приложений .NET Core).</span><span class="sxs-lookup"><span data-stu-id="d079e-130">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

### <a name="consider"></a><span data-ttu-id="d079e-131">Consider</span><span class="sxs-lookup"><span data-stu-id="d079e-131">Consider</span></span>

<span data-ttu-id="d079e-132">При переносе приложения .NET Framework Windows Forms необходимо учесть ряд аспектов.</span><span class="sxs-lookup"><span data-stu-id="d079e-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="d079e-133">Удостоверьтесь, что ваше приложение подходит для переноса.</span><span class="sxs-lookup"><span data-stu-id="d079e-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="d079e-134">Воспользуйтесь [анализатором переносимости .NET](../../standard/analyzers/portability-analyzer.md), чтобы выяснить, можно ли перенести проект в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d079e-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="d079e-135">Если у проекта есть проблемы с .NET Core 3.0, анализатор поможет их обнаружить.</span><span class="sxs-lookup"><span data-stu-id="d079e-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="d079e-136">Вы используете другую версию Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d079e-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="d079e-137">После выпуска .NET Core 3.0 предварительной версии 1 исходный код Windows Forms был размещен в свободном доступе на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="d079e-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open source on GitHub.</span></span> <span data-ttu-id="d079e-138">Код .NET Core Windows Forms является вилкой с базой кода .NET Framework Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d079e-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="d079e-139">Возможно, в используемой вами версии есть некоторые отличия и приложение не удастся перенести.</span><span class="sxs-lookup"><span data-stu-id="d079e-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="d079e-140">Помочь с переносом может [пакет обеспечения совместимости Windows][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="d079e-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="d079e-141">Некоторые API, доступные в .NET Framework, недоступны в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d079e-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="d079e-142">[Пакет обеспечения совместимости Windows][compat-pack] поддерживает многие из этих API и может обеспечить приложению Windows Forms совместимость с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="d079e-143">Обновите пакеты NuGet, используемые в проекте.</span><span class="sxs-lookup"><span data-stu-id="d079e-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="d079e-144">Рекомендуется обновить пакеты NuGet до последней версии перед переносом.</span><span class="sxs-lookup"><span data-stu-id="d079e-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="d079e-145">Если ваше приложение ссылается на пакеты NuGet, обновите их до последней версии.</span><span class="sxs-lookup"><span data-stu-id="d079e-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="d079e-146">Убедитесь, что сборка приложения выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="d079e-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="d079e-147">Если после обновления возникают ошибки пакетов, установите предыдущую версию пакетов, которая не нарушает работу вашего кода.</span><span class="sxs-lookup"><span data-stu-id="d079e-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="d079e-148">Создание проекта пакета SDK</span><span class="sxs-lookup"><span data-stu-id="d079e-148">Create a new SDK project</span></span>

<span data-ttu-id="d079e-149">Проект .NET Core 3.0 необходимо создать в другом каталоге, а не в том, где находится проект .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-149">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="d079e-150">Если разместить проекты в одном каталоге, могут возникнуть конфликты с файлами, создаваемыми в каталоге **obj**.</span><span class="sxs-lookup"><span data-stu-id="d079e-150">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="d079e-151">В этом примере мы создадим каталог с именем **MyFormsAppCore** в каталоге **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="d079e-151">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="d079e-152">Далее необходимо создать проект **MyFormsCore.csproj** в каталоге **MyFormsAppCore**.</span><span class="sxs-lookup"><span data-stu-id="d079e-152">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="d079e-153">Можно создать этот файл вручную с помощью любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="d079e-153">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="d079e-154">Вставьте следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="d079e-154">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d079e-155">Если вы не хотите вручную создавать файл проекта, можно воспользоваться Visual Studio или пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-155">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="d079e-156">Но необходимо удалить все остальные файлы, созданные с помощью шаблона проекта, за исключением файла проекта.</span><span class="sxs-lookup"><span data-stu-id="d079e-156">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="d079e-157">Чтобы использовать пакет SDK, выполните следующую команду из каталога **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="d079e-157">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="d079e-158">После создания **MyFormsCore.csproj** структура каталогов должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d079e-158">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="d079e-159">С помощью Visual Studio или .NET Core CLI добавьте проект **MyFormsCore.csproj** в файл **MyApps.sln** из каталога **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="d079e-159">Add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="d079e-160">Устранение ошибки со сведениями о сборке</span><span class="sxs-lookup"><span data-stu-id="d079e-160">Fix assembly info generation</span></span>

<span data-ttu-id="d079e-161">Проекты Windows Forms, созданные с помощью .NET Framework, содержат файл `AssemblyInfo.cs` с атрибутами сборки, такими как версия создаваемой сборки.</span><span class="sxs-lookup"><span data-stu-id="d079e-161">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="d079e-162">В проектах, созданных с помощью пакета SDK, эти сведения создаются автоматически на основе файла проекта.</span><span class="sxs-lookup"><span data-stu-id="d079e-162">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="d079e-163">Наличие двух типов файлов со сведениями о сборке приводит к конфликту.</span><span class="sxs-lookup"><span data-stu-id="d079e-163">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="d079e-164">Чтобы устранить эту проблему, нужно отключить автоматическое создание такого файла, и тогда в проекте будет использоваться существующий файл `AssemblyInfo.cs`.</span><span class="sxs-lookup"><span data-stu-id="d079e-164">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="d079e-165">В главный узел `<PropertyGroup>` необходимо добавить три параметра.</span><span class="sxs-lookup"><span data-stu-id="d079e-165">There are three settings to add to the main `<PropertyGroup>` node.</span></span>

- <span data-ttu-id="d079e-166">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="d079e-166">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="d079e-167">Если задать этому свойству значение `false`, атрибуты сборки создаваться не будут.</span><span class="sxs-lookup"><span data-stu-id="d079e-167">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="d079e-168">Это позволит избежать конфликта с существующим файлом `AssemblyInfo.cs` из проекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-168">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="d079e-169">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="d079e-169">**AssemblyName**</span></span>\
<span data-ttu-id="d079e-170">Значением этого свойства является выходной двоичный файл, создаваемый при сборке.</span><span class="sxs-lookup"><span data-stu-id="d079e-170">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="d079e-171">К имени не требуется добавлять расширение.</span><span class="sxs-lookup"><span data-stu-id="d079e-171">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="d079e-172">Например, если задать `MyCoreApp`, будет создан файл `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="d079e-172">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="d079e-173">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="d079e-173">**RootNamespace**</span></span>\
<span data-ttu-id="d079e-174">Это пространство имен по умолчанию, используемое в проекте.</span><span class="sxs-lookup"><span data-stu-id="d079e-174">The default namespace used by your project.</span></span> <span data-ttu-id="d079e-175">Оно должно соответствовать пространству имен по умолчанию проекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-175">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="d079e-176">Добавьте эти три элемента в узел `<PropertyGroup>` файла `MyFormsCore.csproj`.</span><span class="sxs-lookup"><span data-stu-id="d079e-176">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="d079e-177">Добавление исходного кода</span><span class="sxs-lookup"><span data-stu-id="d079e-177">Add source code</span></span>

<span data-ttu-id="d079e-178">Сейчас проект **MyFormsCore.csproj** не может компилировать код.</span><span class="sxs-lookup"><span data-stu-id="d079e-178">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="d079e-179">По умолчанию проекты .NET Core автоматически добавляют весь исходный код в текущий каталог и все дочерние каталоги.</span><span class="sxs-lookup"><span data-stu-id="d079e-179">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="d079e-180">Необходимо настроить проект так, чтобы добавлять код из проекта .NET Framework, используя относительный путь.</span><span class="sxs-lookup"><span data-stu-id="d079e-180">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="d079e-181">Если в вашем проекте .NET Framework используются файлы **RESX** для значков и ресурсов форм, их также необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="d079e-181">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span>

<span data-ttu-id="d079e-182">Добавьте в проект указанный ниже узел `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="d079e-182">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="d079e-183">Каждая инструкция содержит стандартную маску файла, охватывающую дочерние каталоги.</span><span class="sxs-lookup"><span data-stu-id="d079e-183">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="d079e-184">Кроме того, можно создать запись `<Compile>` или `<EmbeddedResource>` для каждого файла в проекте .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-184">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="d079e-185">Добавление пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="d079e-185">Add NuGet packages</span></span>

<span data-ttu-id="d079e-186">Добавьте в проект .NET Core все пакеты NuGet, на которые ссылается проект .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-186">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span>

<span data-ttu-id="d079e-187">В вашем приложении .NET Framework Windows Forms, скорее всего, есть файл **packages.config**, содержащий список всех пакетов NuGet, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="d079e-187">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="d079e-188">Этот список поможет вам определить, какие пакеты NuGet нужно добавить в проект .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-188">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="d079e-189">Например, если проект .NET Framework ссылается на пакеты NuGet `MetroFramework`, `MetroFramework.Design` и `MetroFramework.Fonts`, добавьте каждый из них в проект с помощью Visual Studio или .NET Core CLI из каталога **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="d079e-189">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="d079e-190">Приведенные выше команды добавляют следующие ссылки на пакеты NuGet в проект **MyFormsCore.csproj**.</span><span class="sxs-lookup"><span data-stu-id="d079e-190">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="d079e-191">Перенос библиотек элементов управления</span><span class="sxs-lookup"><span data-stu-id="d079e-191">Port control libraries</span></span>

<span data-ttu-id="d079e-192">Если вы переносите проект библиотеки элементов управления Windows Forms, действия будут такими же, как при переносе проекта приложения .NET Framework Windows Forms, за несколькими исключениями.</span><span class="sxs-lookup"><span data-stu-id="d079e-192">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="d079e-193">При этом выполняется сборка не исполняемого файла, а библиотеки.</span><span class="sxs-lookup"><span data-stu-id="d079e-193">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="d079e-194">Различия при переносе проекта исполняемого файла и проекта библиотеки, помимо путей для масок файлов с исходным кодом, сводятся к минимуму.</span><span class="sxs-lookup"><span data-stu-id="d079e-194">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="d079e-195">Используя пример из предыдущего шага, расширим перечень проектов и файлов, с которыми мы работаем.</span><span class="sxs-lookup"><span data-stu-id="d079e-195">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="d079e-196">Файл</span><span class="sxs-lookup"><span data-stu-id="d079e-196">File</span></span> | <span data-ttu-id="d079e-197">Описание</span><span class="sxs-lookup"><span data-stu-id="d079e-197">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="d079e-198">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="d079e-198">**MyApps.sln**</span></span> | <span data-ttu-id="d079e-199">Имя файла решения.</span><span class="sxs-lookup"><span data-stu-id="d079e-199">The name of the solution file.</span></span> |
| <span data-ttu-id="d079e-200">**MyControls.csproj**</span><span class="sxs-lookup"><span data-stu-id="d079e-200">**MyControls.csproj**</span></span> | <span data-ttu-id="d079e-201">Имя проекта библиотеки элементов управления Windows Forms, который нужно перенести.</span><span class="sxs-lookup"><span data-stu-id="d079e-201">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| <span data-ttu-id="d079e-202">**MyControlsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="d079e-202">**MyControlsCore.csproj**</span></span> | <span data-ttu-id="d079e-203">Имя создаваемого проекта библиотеки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-203">The name of the new .NET Core library project you create.</span></span> |
| <span data-ttu-id="d079e-204">**MyCoreControls.dll**</span><span class="sxs-lookup"><span data-stu-id="d079e-204">**MyCoreControls.dll**</span></span> | <span data-ttu-id="d079e-205">Библиотека элементов управления Windows Forms в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-205">The .NET Core Windows Forms Controls library.</span></span> |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

<span data-ttu-id="d079e-206">Рассмотрим различия между проектом `MyControlsCore.csproj` и ранее созданным проектом `MyFormsCore.csproj`.</span><span class="sxs-lookup"><span data-stu-id="d079e-206">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

<span data-ttu-id="d079e-207">Ниже приведен пример, как мог бы выглядеть файл проекта библиотеки элементов управления Windows Forms в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-207">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="d079e-208">Как можно видеть, узел `<OutputType>` был удален, поэтому компилятор создает библиотеку, а не исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="d079e-208">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="d079e-209">Узлы `<AssemblyName>` и `<RootNamespace>` были изменены.</span><span class="sxs-lookup"><span data-stu-id="d079e-209">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="d079e-210">В частности, узел `<RootNamespace>` должен совпадать с пространством имен переносимой библиотеки элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d079e-210">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="d079e-211">Наконец, узлы `<Compile>` и `<EmbeddedResource>` были откорректированы и теперь указывают на папку переносимой библиотеки элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d079e-211">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="d079e-212">Теперь в главном проекте .NET Core **MyFormsCore.csproj** добавьте ссылку на новую библиотеку элементов управления Windows Forms в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-212">Next, in the main .NET Core **MyFormsCore.csproj** project, add a reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="d079e-213">Добавьте ссылку с помощью Visual Studio или .NET Core CLI из каталога **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="d079e-213">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="d079e-214">Предыдущая команда добавляет следующую ссылку в проект **MyFormsCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="d079e-214">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a><span data-ttu-id="d079e-215">Проблемы с компиляцией</span><span class="sxs-lookup"><span data-stu-id="d079e-215">Compilation problems</span></span>

<span data-ttu-id="d079e-216">Если возникают проблемы при сборке проектов, причина может быть в том, что вы используете некоторые API только для Windows, которые доступны в .NET Framework, но недоступны в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-216">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="d079e-217">Попробуйте добавить в свой проект такой пакет NuGet, как [пакет обеспечения совместимости Windows][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="d079e-217">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="d079e-218">Этот пакет выполняется только в среде Windows и добавляет около 20 000 API Windows в проекты .NET Core и .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d079e-218">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="d079e-219">Предыдущая команда добавляет следующую ссылку в проект **MyFormsCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="d079e-219">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="d079e-220">Конструктор Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d079e-220">Windows Forms Designer</span></span>

<span data-ttu-id="d079e-221">Как упоминалось выше, Visual Studio 2019 поддерживает конструктор Forms только в проектах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-221">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="d079e-222">Создав параллельный проект .NET Core, можно проверить его работу в .NET Core, используя при этом конструктор форм в проекте .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-222">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="d079e-223">В файле решения будут присутствовать оба проекта — NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-223">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="d079e-224">Добавляйте и создавайте формы и элементы управления в проекте .NET Framework, а стандартные маски файлов, добавленные нами в проекты .NET Core, позволят автоматически добавлять новые или измененные файлы в проекты .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-224">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="d079e-225">Когда в Visual Studio 2019 будет добавлена поддержка конструктора Windows Forms, можно скопировать и вставить содержимое файла проекта .NET Core в файл проекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d079e-225">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="d079e-226">Затем можно удалить стандартные маски файлов, добавленные с помощью элементов `<Source>` и `<EmbeddedResource>`.</span><span class="sxs-lookup"><span data-stu-id="d079e-226">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="d079e-227">Исправьте пути ссылок проекта, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="d079e-227">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="d079e-228">Это позволит полноценно преобразовать проект .NET Framework в проект .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-228">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d079e-229">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d079e-229">Next steps</span></span>

- <span data-ttu-id="d079e-230">Ознакомьтесь со [списком критических изменений, касающихся перехода с .NET Framework на .NET Core](../compatibility/fx-core.md).</span><span class="sxs-lookup"><span data-stu-id="d079e-230">Learn about [breaking changes from .NET Framework to .NET Core](../compatibility/fx-core.md).</span></span>
- <span data-ttu-id="d079e-231">Дополнительные сведения о [пакете обеспечения совместимости Windows][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="d079e-231">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="d079e-232">[Видео о переносе](https://www.youtube.com/watch?v=upVQEUc_KwU) проекта Windows Forms из .NET Framework в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d079e-232">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
