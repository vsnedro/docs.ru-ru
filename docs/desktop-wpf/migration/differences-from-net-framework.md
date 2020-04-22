---
title: Различия между рамками .NET и ядром .NET
description: Описывает различия между реализацией .NET Framework Фонда презентаций Windows (WPF) и .NET Core WPF. При миграции приложения следует учитывать эти несовместимость.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 341e576f17c522fbcbb9c417176e9d4a13ab1b18
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021841"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="493be-104">Различия в WPF</span><span class="sxs-lookup"><span data-stu-id="493be-104">Differences in WPF</span></span>

<span data-ttu-id="493be-105">В этой статье описаны различия между Фондом презентаций Windows (WPF) на .NET Core и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="493be-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="493be-106">WPF для .NET Core — это платформа с [открытым исходным кодом](https://github.com/dotnet/wpf) с открытым исходным кодом, раздвинутый с исходным кодом.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="493be-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="493be-107">Есть несколько особенностей рамочного соглашения .NET, которые .NET Core не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="493be-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="493be-108">Для получения дополнительной информации [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md)о неподдерживаемых технологиях см.</span><span class="sxs-lookup"><span data-stu-id="493be-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="493be-109">Проекты в стиле SDK</span><span class="sxs-lookup"><span data-stu-id="493be-109">SDK-style projects</span></span>

<span data-ttu-id="493be-110">.NET Core использует файлы проектов в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="493be-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="493be-111">Эти файлы проекта отличаются от традиционных файлов проекта .NET Framework, управляемых Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="493be-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="493be-112">Чтобы перенести приложения .NET Framework WPF в ядро .NET, необходимо преобразовать свои проекты.</span><span class="sxs-lookup"><span data-stu-id="493be-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="493be-113">Для получения дополнительной информации [см.](convert-project-from-net-framework.md)</span><span class="sxs-lookup"><span data-stu-id="493be-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="493be-114">Ссылки на пакет NuGet</span><span class="sxs-lookup"><span data-stu-id="493be-114">NuGet package references</span></span>

<span data-ttu-id="493be-115">Если приложение .NET Framework перечисляет свои зависимости NuGet в файле [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) *packages.config,* переноситесь в формат:</span><span class="sxs-lookup"><span data-stu-id="493be-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="493be-116">В Visual Studio откройте панель **Solution Explorer.**</span><span class="sxs-lookup"><span data-stu-id="493be-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="493be-117">В вашем проекте WPF, правой кнопкой мыши **packages.config** > **Мигрировать Migrate packages.config к PackageReference**.</span><span class="sxs-lookup"><span data-stu-id="493be-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![Обновление до PackageReference](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="493be-119">Появится диалог, показывающий рассчитанные зависимые от NuGet верхнего уровня и спрашивающий, какие другие пакеты NuGet следует продвигать на высший уровень.</span><span class="sxs-lookup"><span data-stu-id="493be-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="493be-120">Выберите **OK** и файл *packages.config* будет `<PackageReference>` удален из проекта, и элементы будут добавлены в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="493be-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="493be-121">Когда ваш `<PackageReference>`проект использует, пакеты не хранятся локально в папке *пакетов,* они хранятся по всему миру.</span><span class="sxs-lookup"><span data-stu-id="493be-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="493be-122">Откройте файл проекта `<Analyzer>` и удалите все элементы, относящееся к папке *Пакетов.*</span><span class="sxs-lookup"><span data-stu-id="493be-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="493be-123">Эти анализаторы автоматически включаются со ссылками на пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="493be-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="493be-124">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="493be-124">Code Access Security</span></span>

<span data-ttu-id="493be-125">Code Access Security (CAS) не поддерживается .NET Core или WPF для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="493be-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="493be-126">Все функции, связанные с CAS, рассматриваются в соответствии с предположением о полном доверии.</span><span class="sxs-lookup"><span data-stu-id="493be-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="493be-127">WPF для .NET Core удаляет код, связанный с CAS.</span><span class="sxs-lookup"><span data-stu-id="493be-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="493be-128">Публичная поверхность API этих типов по-прежнему существует для обеспечения успеха вызовов в эти типы.</span><span class="sxs-lookup"><span data-stu-id="493be-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="493be-129">Публично определенные типы, связанные с CAS, были перемещены из собраний WPF и в собрания библиотеки Core .NET.</span><span class="sxs-lookup"><span data-stu-id="493be-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the Core .NET library assemblies.</span></span> <span data-ttu-id="493be-130">Сборки WPF имеют набор для переадресов к новому местоположению перемещенных типов.</span><span class="sxs-lookup"><span data-stu-id="493be-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="493be-131">Сборка исходных источников</span><span class="sxs-lookup"><span data-stu-id="493be-131">Source assembly</span></span> | <span data-ttu-id="493be-132">Целевая сборка</span><span class="sxs-lookup"><span data-stu-id="493be-132">Target assembly</span></span> | <span data-ttu-id="493be-133">Тип</span><span class="sxs-lookup"><span data-stu-id="493be-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="493be-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="493be-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="493be-135">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="493be-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="493be-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="493be-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="493be-137">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="493be-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="493be-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="493be-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="493be-139">*System.Windows.Extension.dll*</span><span class="sxs-lookup"><span data-stu-id="493be-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="493be-140">Для минимизации трения порта, функциональность для хранения и извлечения информации, `XamlAccessLevel` связанной со следующими свойствами, была сохранена в типе.</span><span class="sxs-lookup"><span data-stu-id="493be-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="493be-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="493be-141">Next steps</span></span>

- [<span data-ttu-id="493be-142">Узнайте, как портировать приложение .NET Framework WPF в ядро .NET.</span><span class="sxs-lookup"><span data-stu-id="493be-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
