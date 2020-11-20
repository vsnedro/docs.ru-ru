---
ms.openlocfilehash: 87c7abf6a20dd8e9769f3b3b3cbe271d32fd62c3
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507003"
---

### <a name="install-the-sdk"></a><span data-ttu-id="9a891-101">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="9a891-101">Install the SDK</span></span>

<span data-ttu-id="9a891-102">Пакет SDK для .NET позволяет разрабатывать приложения с помощью .NET.</span><span class="sxs-lookup"><span data-stu-id="9a891-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="9a891-103">При установке пакета SDK для .NET не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a891-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="9a891-104">Чтобы установить пакет SDK для .NET, выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="9a891-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="9a891-105">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-5.0** (Не удалось найти пакет dotnet-sdk-5.0), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9a891-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-5.0**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="9a891-106">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9a891-106">Install the runtime</span></span>

<span data-ttu-id="9a891-107">Среда выполнения ASP.NET Core позволяет запускать приложения, созданные с помощью версии .NET без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a891-107">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="9a891-108">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET.</span><span class="sxs-lookup"><span data-stu-id="9a891-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="9a891-109">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="9a891-109">In your terminal, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="9a891-110">Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-5.0** (Не удалось найти пакет aspnetcore-runtime-5.0), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9a891-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-5.0**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="9a891-111">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-5.0` на `dotnet-runtime-5.0`.</span><span class="sxs-lookup"><span data-stu-id="9a891-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo apt-get install -y dotnet-runtime-5.0
```
