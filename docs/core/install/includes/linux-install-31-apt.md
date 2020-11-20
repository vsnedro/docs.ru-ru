---
ms.openlocfilehash: cac1fbd2369277b3a322247a7008f07929502437
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507022"
---

### <a name="install-the-sdk"></a><span data-ttu-id="dc9f5-101">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="dc9f5-101">Install the SDK</span></span>

<span data-ttu-id="dc9f5-102">Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="dc9f5-103">При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-103">If you install the .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="dc9f5-104">Чтобы установить пакет SDK для .NET Core, выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-104">To install the .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="dc9f5-105">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-3.1** (Не удалось найти пакет dotnet-sdk-3.1), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="dc9f5-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="dc9f5-106">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="dc9f5-106">Install the runtime</span></span>

<span data-ttu-id="dc9f5-107">Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="dc9f5-108">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="dc9f5-109">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="dc9f5-110">Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-3.1** (Не удалось найти пакет aspnetcore-runtime-3.1), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="dc9f5-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="dc9f5-111">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-3.1` на `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="dc9f5-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-3.1
```
