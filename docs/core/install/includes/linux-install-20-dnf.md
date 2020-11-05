---
ms.openlocfilehash: 787b0a04c5bf312ad3f3e7834664e70dae9678e0
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93136120"
---

### <a name="install-the-sdk"></a><span data-ttu-id="f381d-101">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f381d-101">Install the SDK</span></span>

<span data-ttu-id="f381d-102">Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f381d-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="f381d-103">При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f381d-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f381d-104">Чтобы установить пакет SDK для .NET Core, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f381d-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-2.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="f381d-105">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f381d-105">Install the runtime</span></span>

<span data-ttu-id="f381d-106">Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f381d-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="f381d-107">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f381d-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="f381d-108">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f381d-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-2.0
```

<span data-ttu-id="f381d-109">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-2.0` на `dotnet-runtime-2.0`.</span><span class="sxs-lookup"><span data-stu-id="f381d-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.0` in the previous command with `dotnet-runtime-2.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-2.0
```
