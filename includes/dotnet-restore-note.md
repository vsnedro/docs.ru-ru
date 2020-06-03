---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102750"
---
<span data-ttu-id="dc75b-101">Вам не нужно выполнять команду [`dotnet restore`](~/docs/core/tools/dotnet-restore.md), так как она выполняется неявно всеми командами, которые требуют восстановления, например `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` и `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="dc75b-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="dc75b-102">Чтобы отключить неявное восстановление, используйте параметр `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="dc75b-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="dc75b-103">Команду `dotnet restore` по-прежнему удобно использовать в некоторых сценариях, где необходимо явное восстановление, например в [сборках с использованием непрерывной интеграции в Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) или системах сборки, где требуется явно контролировать время восстановления.</span><span class="sxs-lookup"><span data-stu-id="dc75b-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="dc75b-104">Сведения об управлении веб-каналами NuGet см. в [документации по `dotnet restore`](../docs/core/tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="dc75b-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>
