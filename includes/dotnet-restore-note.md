---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102750"
---
Вам не нужно выполнять команду [`dotnet restore`](~/docs/core/tools/dotnet-restore.md), так как она выполняется неявно всеми командами, которые требуют восстановления, например `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` и `dotnet pack`. Чтобы отключить неявное восстановление, используйте параметр `--no-restore`.

Команду `dotnet restore` по-прежнему удобно использовать в некоторых сценариях, где необходимо явное восстановление, например в [сборках с использованием непрерывной интеграции в Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) или системах сборки, где требуется явно контролировать время восстановления.

Сведения об управлении веб-каналами NuGet см. в [документации по `dotnet restore`](../docs/core/tools/dotnet-restore.md).
