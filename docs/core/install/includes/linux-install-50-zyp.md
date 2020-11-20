---
ms.openlocfilehash: ed269683f5c4569c21ae53e9a3c1ec65eb5ebd43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506872"
---

### <a name="install-the-sdk"></a><span data-ttu-id="6d4f9-101">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="6d4f9-101">Install the SDK</span></span>

<span data-ttu-id="6d4f9-102">Пакет SDK для .NET позволяет разрабатывать приложения с помощью .NET.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="6d4f9-103">При установке пакета SDK для .NET не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="6d4f9-104">Чтобы установить пакет SDK для .NET, выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo zypper install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="6d4f9-105">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6d4f9-105">Install the runtime</span></span>

<span data-ttu-id="6d4f9-106">Среда выполнения ASP.NET Core позволяет запускать приложения, созданные с помощью версии .NET без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="6d4f9-107">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="6d4f9-108">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-108">In your terminal, run the following commands:</span></span>

```bash
sudo zypper install aspnetcore-runtime-5.0
```

<span data-ttu-id="6d4f9-109">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-5.0` на `dotnet-runtime-5.0`.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo zypper install dotnet-runtime-5.0
```
