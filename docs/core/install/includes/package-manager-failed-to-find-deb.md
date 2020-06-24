---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602750"
---

<span data-ttu-id="f7e2a-101">Если появляется сообщение об ошибке, похожее на **Unable to locate package {netcore-package}** (Не удалось найти пакет {netcore-package}), выполните проведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-101">If you receive an error message similar to **Unable to locate package {netcore-package}**, run the following commands.</span></span>

<span data-ttu-id="f7e2a-102">В следующем наборе команд есть два заполнителя.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="f7e2a-103">Этот заполнитель представляет собой устанавливаемый пакет .NET Core, например `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="f7e2a-104">Он используется в приведенной ниже команде `sudo apt-get install`.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="f7e2a-105">Этот заполнитель представляет собой используемую версию Linux.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="f7e2a-106">Он используется в приведенной ниже команде `wget`.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="f7e2a-107">Попробуйте очистить список пакетов:</span><span class="sxs-lookup"><span data-stu-id="f7e2a-107">Try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

<span data-ttu-id="f7e2a-108">Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.</span><span class="sxs-lookup"><span data-stu-id="f7e2a-108">If that doesn't work, you can run a manual install with the following commands:</span></span>
