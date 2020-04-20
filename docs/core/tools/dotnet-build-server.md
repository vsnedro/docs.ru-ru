---
title: Команда dotnet build-server
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 02/14/2020
ms.openlocfilehash: 882b697c07aac0e20266f3ad4e6c11888a0b7acc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463724"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="a497a-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="a497a-103">dotnet build-server</span></span>

<span data-ttu-id="a497a-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="a497a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a497a-105">Имя</span><span class="sxs-lookup"><span data-stu-id="a497a-105">Name</span></span>

<span data-ttu-id="a497a-106">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="a497a-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a497a-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a497a-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]

dotnet build-server shutdown -h|--help

dotnet build-server -h|--help
```

## <a name="commands"></a><span data-ttu-id="a497a-108">Команды</span><span class="sxs-lookup"><span data-stu-id="a497a-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="a497a-109">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="a497a-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="a497a-110">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="a497a-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="a497a-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="a497a-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="a497a-112">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a497a-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="a497a-113">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a497a-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="a497a-114">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="a497a-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="a497a-115">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="a497a-115">Shuts down the VB/C# compiler build server.</span></span>
