---
title: 'Использование Управление пакетами с F # для Azure'
description: 'Использование пакет или NuGet для управления зависимостями Azure на F #'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 7816c82e87db113a35fef967886c8c3e27959332
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756238"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="cbaba-103">Управление пакетами для зависимостей F# в Azure</span><span class="sxs-lookup"><span data-stu-id="cbaba-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="cbaba-104">Получение пакетов для разработки Azure несложно при использовании диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="cbaba-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="cbaba-105">Два варианта — [пакет](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="cbaba-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="cbaba-106">Использование пакет</span><span class="sxs-lookup"><span data-stu-id="cbaba-106">Using Paket</span></span>

<span data-ttu-id="cbaba-107">Если вы используете [пакет](https://fsprojects.github.io/Paket/) в качестве диспетчера зависимостей, вы можете использовать это `paket.exe` средство для добавления зависимостей Azure.</span><span class="sxs-lookup"><span data-stu-id="cbaba-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="cbaba-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="cbaba-108">For example:</span></span>

```console
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="cbaba-109">Или, если вы используете [Mono](https://www.mono-project.com/) для кросс-платформенной разработки .NET:</span><span class="sxs-lookup"><span data-stu-id="cbaba-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="cbaba-110">При этом будет добавлен `WindowsAzure.Storage` набор зависимостей пакета для проекта в текущем каталоге, изменен `paket.dependencies` файл и загружен пакет.</span><span class="sxs-lookup"><span data-stu-id="cbaba-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="cbaba-111">Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cbaba-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> paket install
```

<span data-ttu-id="cbaba-112">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cbaba-112">Or, for Mono development:</span></span>

```console
> mono paket.exe install
```

<span data-ttu-id="cbaba-113">Вы можете обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cbaba-113">You can update all your package dependencies to the latest version like this:</span></span>

```console
> paket update
```

<span data-ttu-id="cbaba-114">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cbaba-114">Or, for Mono development:</span></span>

```console
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="cbaba-115">Использование NuGet</span><span class="sxs-lookup"><span data-stu-id="cbaba-115">Using NuGet</span></span>

<span data-ttu-id="cbaba-116">Если вы используете [NuGet](https://www.nuget.org/) в качестве диспетчера зависимостей, это средство можно использовать `nuget.exe` для добавления зависимостей Azure.</span><span class="sxs-lookup"><span data-stu-id="cbaba-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="cbaba-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="cbaba-117">For example:</span></span>

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="cbaba-118">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cbaba-118">Or, for Mono development:</span></span>

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="cbaba-119">Это приведет к добавлению `WindowsAzure.Storage` набора зависимостей пакета для проекта в текущем каталоге и загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="cbaba-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="cbaba-120">Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cbaba-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> nuget restore
```

<span data-ttu-id="cbaba-121">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cbaba-121">Or, for Mono development:</span></span>

```console
> mono nuget.exe restore
```

<span data-ttu-id="cbaba-122">Вы можете обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cbaba-122">You can update all your package dependencies to the latest version like this:</span></span>

```console
> nuget update
```

<span data-ttu-id="cbaba-123">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cbaba-123">Or, for Mono development:</span></span>

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="cbaba-124">Ссылки на сборки</span><span class="sxs-lookup"><span data-stu-id="cbaba-124">Referencing Assemblies</span></span>

<span data-ttu-id="cbaba-125">Чтобы использовать пакеты в скрипте F #, необходимо сослаться на сборки, содержащиеся в пакетах, с помощью `#r` директивы.</span><span class="sxs-lookup"><span data-stu-id="cbaba-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="cbaba-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="cbaba-126">For example:</span></span>

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="cbaba-127">Как видите, необходимо указать относительный путь к библиотеке DLL и полное имя библиотеки DLL, которое может не совпадать с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="cbaba-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="cbaba-128">Путь будет содержать версию платформы и, возможно, номер версии пакета.</span><span class="sxs-lookup"><span data-stu-id="cbaba-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="cbaba-129">Чтобы найти все установленные сборки, можно использовать в командной строке Windows нечто подобное:</span><span class="sxs-lookup"><span data-stu-id="cbaba-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="cbaba-130">Или в оболочке UNIX примерно так:</span><span class="sxs-lookup"><span data-stu-id="cbaba-130">Or in a Unix shell, something like this:</span></span>

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="cbaba-131">При этом будут предоставлены пути к установленным сборкам.</span><span class="sxs-lookup"><span data-stu-id="cbaba-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="cbaba-132">После этого можно выбрать правильный путь к версии платформы.</span><span class="sxs-lookup"><span data-stu-id="cbaba-132">From there, you can select the correct path for your framework version.</span></span>
