---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132952"
---

<span data-ttu-id="1d5a7-101">Если появляется сообщение об ошибке, похожее на **Не удалось найти пакет {netcore-package}** или **Не удалось установить некоторые пакеты**, выполните проведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-101">If you receive an error message similar to **Unable to locate package {netcore-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="1d5a7-102">В следующем наборе команд есть два заполнителя.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="1d5a7-103">Этот заполнитель представляет собой устанавливаемый пакет .NET Core, например `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="1d5a7-104">Он используется в приведенной ниже команде `sudo apt-get install`.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="1d5a7-105">Этот заполнитель представляет собой используемую версию Linux.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="1d5a7-106">Он используется в приведенной ниже команде `wget`.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="1d5a7-107">Сначала попробуйте очистить список пакетов.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="1d5a7-108">Затем попробуйте установить .NET Core еще раз.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-108">Then, try to install .NET Core again.</span></span> <span data-ttu-id="1d5a7-109">Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.</span><span class="sxs-lookup"><span data-stu-id="1d5a7-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
