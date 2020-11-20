---
ms.openlocfilehash: 8315b4f86dddfbb68534bc9ad3ad74907daa03d0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507067"
---

### <a name="install-the-sdk"></a><span data-ttu-id="52485-101">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="52485-101">Install the SDK</span></span>

<span data-ttu-id="52485-102">Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52485-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="52485-103">При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="52485-103">If you install the .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="52485-104">Чтобы установить пакет SDK для .NET Core, выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="52485-104">To install the .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-3.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="52485-105">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="52485-105">Install the runtime</span></span>

<span data-ttu-id="52485-106">Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="52485-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="52485-107">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52485-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="52485-108">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="52485-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.0
```

<span data-ttu-id="52485-109">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-3.0` на `dotnet-runtime-3.0`.</span><span class="sxs-lookup"><span data-stu-id="52485-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.0` in the previous command with `dotnet-runtime-3.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
```
