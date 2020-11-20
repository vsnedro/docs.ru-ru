---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506983"
---

<span data-ttu-id="3eccb-101">Если появляется сообщение об ошибке, похожее на **Не удалось найти пакет {dotnet-package}** или **Не удалось установить некоторые пакеты**, выполните проведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="3eccb-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="3eccb-102">В следующем наборе команд есть два заполнителя.</span><span class="sxs-lookup"><span data-stu-id="3eccb-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="3eccb-103">Этот заполнитель представляет собой устанавливаемый пакет .NET, например `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="3eccb-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="3eccb-104">Это используется в следующей команде `sudo apt-get install`.</span><span class="sxs-lookup"><span data-stu-id="3eccb-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="3eccb-105">Этот заполнитель представляет собой используемую версию Linux.</span><span class="sxs-lookup"><span data-stu-id="3eccb-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="3eccb-106">Он используется в приведенной ниже команде `wget`.</span><span class="sxs-lookup"><span data-stu-id="3eccb-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="3eccb-107">Сначала попробуйте очистить список пакетов.</span><span class="sxs-lookup"><span data-stu-id="3eccb-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="3eccb-108">Затем попробуйте установить .NET еще раз.</span><span class="sxs-lookup"><span data-stu-id="3eccb-108">Then, try to install .NET again.</span></span> <span data-ttu-id="3eccb-109">Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.</span><span class="sxs-lookup"><span data-stu-id="3eccb-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
