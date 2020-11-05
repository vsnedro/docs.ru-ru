---
ms.openlocfilehash: 56f5d27eb9be2f8eb3e335c5ec161dba1bcfdb1e
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135489"
---

### <a name="install-the-sdk"></a><span data-ttu-id="5b6b2-101">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="5b6b2-101">Install the SDK</span></span>

<span data-ttu-id="5b6b2-102">Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="5b6b2-103">При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="5b6b2-104">Чтобы установить пакет SDK для .NET Core, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5b6b2-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="5b6b2-105">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-3.1** (Не удалось найти пакет dotnet-sdk-3.1), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="5b6b2-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="5b6b2-106">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="5b6b2-106">Install the runtime</span></span>

<span data-ttu-id="5b6b2-107">Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="5b6b2-108">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="5b6b2-109">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="5b6b2-110">Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-3.1** (Не удалось найти пакет aspnetcore-runtime-3.1), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="5b6b2-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="5b6b2-111">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-3.1` на `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-3.1
```
