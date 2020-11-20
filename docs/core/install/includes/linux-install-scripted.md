---
ms.openlocfilehash: 07dd58c314c826c426193b829ea1f64669fb888b
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594576"
---

<span data-ttu-id="96c33-101">[Сценарии dotnet-install](../../tools/dotnet-install-script.md) используются для автоматизации установок **пакета SDK** и **среды выполнения** и осуществления таких установок без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="96c33-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="96c33-102">Скрипт можно скачать на странице <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="96c33-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="96c33-103">Этот сценарий по умолчанию устанавливает последнюю версию SDK [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET 3.1.</span><span class="sxs-lookup"><span data-stu-id="96c33-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET 3.1.</span></span> <span data-ttu-id="96c33-104">Чтобы установить текущий выпуск, который может не быть версией LTS, используйте параметр `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="96c33-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="96c33-105">Чтобы вместо пакета SDK установить среду выполнения .NET, используйте параметр `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="96c33-105">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="96c33-106">Вы можете установить определенную версию, указав ее в параметре `-c`.</span><span class="sxs-lookup"><span data-stu-id="96c33-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="96c33-107">Следующая команда устанавливает пакет SDK для .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="96c33-107">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="96c33-108">Дополнительные сведения см. в статье [Справка по скриптам dotnet-install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="96c33-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
