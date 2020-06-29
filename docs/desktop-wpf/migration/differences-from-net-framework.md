---
title: Различия между .NET Core и .NET Framework
description: Описание различий между реализацией Windows Presentation Foundation (WPF) в .NET Framework и .NET Core. При переносе приложения следует учитывать эти несовместимости.
author: adegeo
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 3bedc30046c36d4c5430feedf5854276ebaef8aa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325693"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="1e05f-104">Отличия в WPF</span><span class="sxs-lookup"><span data-stu-id="1e05f-104">Differences in WPF</span></span>

<span data-ttu-id="1e05f-105">В этой статье описываются различия между Windows Presentation Foundation (WPF) в .NET Core и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e05f-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="1e05f-106">WPF для .NET Core — [платформа с открытым исходным кодом](https://github.com/dotnet/wpf), ответвленная от первоначального исходного кода WPF для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e05f-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="1e05f-107">.NET Core не поддерживает несколько функций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e05f-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="1e05f-108">Дополнительные сведения о неподдерживаемых технологиях см. в статье [Технологии .NET Framework, недоступные в .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="1e05f-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="1e05f-109">Проекты в стиле SDK</span><span class="sxs-lookup"><span data-stu-id="1e05f-109">SDK-style projects</span></span>

<span data-ttu-id="1e05f-110">.NET Core использует файлы проектов в стиле пакетов SDK.</span><span class="sxs-lookup"><span data-stu-id="1e05f-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="1e05f-111">Эти файлы проектов отличаются от традиционных файлов проектов .NET Framework, управляемых Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e05f-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="1e05f-112">Для переноса приложений WPF .NET Framework в .NET Core необходимо преобразовать их проекты.</span><span class="sxs-lookup"><span data-stu-id="1e05f-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="1e05f-113">Дополнительные сведения см. в разделе [Руководство по миграции приложений WPF в .NET Core 3.0](convert-project-from-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="1e05f-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="1e05f-114">Ссылки на пакет NuGet</span><span class="sxs-lookup"><span data-stu-id="1e05f-114">NuGet package references</span></span>

<span data-ttu-id="1e05f-115">Если приложение .NET Framework перечисляет зависимости NuGet в файле *packages.config*, выполните миграцию в формат [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files):</span><span class="sxs-lookup"><span data-stu-id="1e05f-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="1e05f-116">В Visual Studio откройте окно **Обозревателя решений**.</span><span class="sxs-lookup"><span data-stu-id="1e05f-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="1e05f-117">В проекте WPF щелкните правой кнопкой мыши **packages.config** > **Перенести packages.config в PackageReference**.</span><span class="sxs-lookup"><span data-stu-id="1e05f-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![Обновление до PackageReference](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="1e05f-119">Откроется диалоговое окно с вычисленными зависимостями NuGet верхнего уровня и вопросом, какие другие пакеты NuGet следует повысить до верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="1e05f-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="1e05f-120">Выберите **ОК**, и файл *packages.config* будет удален из проекта, а элементы `<PackageReference>` будут добавлены в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="1e05f-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="1e05f-121">Если в проекте используется `<PackageReference>`, пакеты не хранятся локально в папке *Пакеты*, они хранятся глобально.</span><span class="sxs-lookup"><span data-stu-id="1e05f-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="1e05f-122">Откройте файл проекта и удалите все элементы `<Analyzer>`, которые ссылаются на папку *Пакеты*.</span><span class="sxs-lookup"><span data-stu-id="1e05f-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="1e05f-123">Эти анализаторы автоматически добавляются к ссылкам на пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="1e05f-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="1e05f-124">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="1e05f-124">Code Access Security</span></span>

<span data-ttu-id="1e05f-125">Управление доступом для кода (CAS) не поддерживается .NET Core или WPF для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1e05f-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="1e05f-126">Все функции, связанные с CAS, работают исходя из предположения полного доверия.</span><span class="sxs-lookup"><span data-stu-id="1e05f-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="1e05f-127">WPF для .NET Core удаляет код, связанный с CAS.</span><span class="sxs-lookup"><span data-stu-id="1e05f-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="1e05f-128">Поверхность открытого API этих типов по-прежнему существует, чтобы обеспечить успешный вызов этих типов.</span><span class="sxs-lookup"><span data-stu-id="1e05f-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="1e05f-129">Открыто определенные типы, связанные с CAS, были перемещены из сборок WPF в сборки библиотеки Core .NET.</span><span class="sxs-lookup"><span data-stu-id="1e05f-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the Core .NET library assemblies.</span></span> <span data-ttu-id="1e05f-130">В этих сборках WPF установлена пересылка типов к новому расположению перемещенных типов.</span><span class="sxs-lookup"><span data-stu-id="1e05f-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="1e05f-131">Исходная сборка</span><span class="sxs-lookup"><span data-stu-id="1e05f-131">Source assembly</span></span> | <span data-ttu-id="1e05f-132">Целевая сборка</span><span class="sxs-lookup"><span data-stu-id="1e05f-132">Target assembly</span></span> | <span data-ttu-id="1e05f-133">Type</span><span class="sxs-lookup"><span data-stu-id="1e05f-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="1e05f-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="1e05f-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="1e05f-135">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="1e05f-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="1e05f-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="1e05f-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="1e05f-137">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="1e05f-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="1e05f-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="1e05f-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="1e05f-139">*System.Windows.Extension.dll*</span><span class="sxs-lookup"><span data-stu-id="1e05f-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="1e05f-140">Чтобы свести к минимуму трения при переносе, функции хранения и извлечения информации, связанной со следующими свойствами, были оставлены в типе `XamlAccessLevel`.</span><span class="sxs-lookup"><span data-stu-id="1e05f-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="1e05f-141">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1e05f-141">Next steps</span></span>

- [<span data-ttu-id="1e05f-142">Узнайте, как перенести приложение WPF .NET Framework в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1e05f-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
