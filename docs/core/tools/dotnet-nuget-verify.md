---
title: Команда dotnet nuget verify
description: Команда otnet nuget verify проверяет подписанный пакет.
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957117"
---
# <a name="dotnet-nuget-verify"></a><span data-ttu-id="6a7e3-103">dotnet nuget verify</span><span class="sxs-lookup"><span data-stu-id="6a7e3-103">dotnet nuget verify</span></span>

<span data-ttu-id="6a7e3-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET 5.0.100-rc.2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="6a7e3-104">**This article applies to:** ✔️ .NET 5.0.100-rc.2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6a7e3-105">Имя</span><span class="sxs-lookup"><span data-stu-id="6a7e3-105">Name</span></span>

<span data-ttu-id="6a7e3-106">`dotnet nuget verify` — проверяет подписанный пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-106">`dotnet nuget verify` - Verifies a signed NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6a7e3-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6a7e3-107">Synopsis</span></span>

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a><span data-ttu-id="6a7e3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="6a7e3-108">Description</span></span>

<span data-ttu-id="6a7e3-109">Команда `dotnet nuget verify` проверяет подписанный пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-109">The `dotnet nuget verify` command verifies a signed NuGet package.</span></span>

## <a name="arguments"></a><span data-ttu-id="6a7e3-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6a7e3-110">Arguments</span></span>

- **`package-path(s)`**

  <span data-ttu-id="6a7e3-111">Указывает путь к файлу проверяемого пакета.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-111">Specifies the file path to the package(s) to be verified.</span></span> <span data-ttu-id="6a7e3-112">Для проверки нескольких пакетов можно передать несколько аргументов с расположением.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-112">Multiple position arguments can be passed in to verify multiple packages.</span></span>

## <a name="options"></a><span data-ttu-id="6a7e3-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a7e3-113">Options</span></span>

- **`--all`**

  <span data-ttu-id="6a7e3-114">Указывает, что для пакетов нужно выполнить все возможные проверки.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-114">Specifies that all verifications possible should be performed on the package(s).</span></span> <span data-ttu-id="6a7e3-115">По умолчанию проверяются только `signatures`.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-115">By default, only `signatures` are verified.</span></span>

> [!NOTE]
> <span data-ttu-id="6a7e3-116">В настоящее время эта команда поддерживает только проверку `signature`.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-116">This command currently supports only `signature` verification.</span></span>

- **`--certificate-fingerprint <FINGERPRINT>`**

  <span data-ttu-id="6a7e3-117">Убедитесь, что сертификат подписавшего лица совпадает с одним из указанных отпечатков `SHA256`.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-117">Verify that the signer certificate matches with one of the specified `SHA256` fingerprints.</span></span> <span data-ttu-id="6a7e3-118">Этот параметр можно указать несколько раз, чтобы предоставить несколько отпечатков.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-118">This option can be supplied multiple times to provide multiple fingerprints.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="6a7e3-119">Задает уровень детализации MSBuild.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-119">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="6a7e3-120">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-120">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6a7e3-121">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-121">The default is `normal`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="6a7e3-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="6a7e3-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="6a7e3-123">Examples</span></span>

- <span data-ttu-id="6a7e3-124">Проверка *foo.nupkg*.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-124">Verify *foo.nupkg*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- <span data-ttu-id="6a7e3-125">Проверка нескольких пакетов NuGet: *foo.nupkg* и *всех файлов .nupkg в указанном каталоге*.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-125">Verify multiple NuGet packages - *foo.nupkg* and *all .nupkg files in the directory specified*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- <span data-ttu-id="6a7e3-126">Проверка того, что сигнатура *foo.nupkg* соответствует указанному отпечатку сертификата.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-126">Verify *foo.nupkg* signature matches with the specified certificate fingerprint:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- <span data-ttu-id="6a7e3-127">Проверка того, что сигнатура *foo.nupkg* соответствует одному из указанных отпечатков сертификата.</span><span class="sxs-lookup"><span data-stu-id="6a7e3-127">Verify *foo.nupkg* signature matches with one of the specified certificate fingerprints:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
