---
title: Команда dotnet nuget update source
description: Команда dotnet nuget update source обновляет существующий источник в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: a8658c78c095ad4b9272d97200e1d6466cbe658b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537858"
---
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="dade2-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="dade2-103">dotnet nuget update source</span></span>

<span data-ttu-id="dade2-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="dade2-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="dade2-105">name</span><span class="sxs-lookup"><span data-stu-id="dade2-105">Name</span></span>

<span data-ttu-id="dade2-106">`dotnet nuget update source` — обновление источника NuGet.</span><span class="sxs-lookup"><span data-stu-id="dade2-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dade2-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dade2-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a><span data-ttu-id="dade2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="dade2-108">Description</span></span>

<span data-ttu-id="dade2-109">Команда `dotnet nuget update source` обновляет существующий источник в файлах конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="dade2-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="dade2-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="dade2-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="dade2-111">Имя источника.</span><span class="sxs-lookup"><span data-stu-id="dade2-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="dade2-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="dade2-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="dade2-113">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="dade2-113">The NuGet configuration file.</span></span> <span data-ttu-id="dade2-114">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="dade2-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="dade2-115">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="dade2-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="dade2-116">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="dade2-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="dade2-117">Пароль, используемый при подключении к источнику, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="dade2-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="dade2-118">Путь к источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="dade2-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="dade2-119">Включает сохранение учетных данных переносимого источника пакетов путем отключения шифрования паролей.</span><span class="sxs-lookup"><span data-stu-id="dade2-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="dade2-120">Имя пользователя, используемое при подключении к источнику, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="dade2-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="dade2-121">Разделенный запятыми список допустимых типов проверки подлинности для этого источника.</span><span class="sxs-lookup"><span data-stu-id="dade2-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="dade2-122">Задайте значение `basic`, если сервер объявляет NTLM или Negotiate. Ваши учетные данные следует отправлять с помощью базового механизма, например, при использовании PAT с локальным Azure DevOps Server.</span><span class="sxs-lookup"><span data-stu-id="dade2-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="dade2-123">К другим допустимым значениям относятся `negotiate`, `kerberos`, `ntlm` и `digest`, но они вряд ли будут полезны.</span><span class="sxs-lookup"><span data-stu-id="dade2-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="dade2-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="dade2-124">Examples</span></span>

- <span data-ttu-id="dade2-125">Обновите источник с именем `mySource`:</span><span class="sxs-lookup"><span data-stu-id="dade2-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="dade2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="dade2-126">See also</span></span>

- [<span data-ttu-id="dade2-127">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="dade2-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="dade2-128">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="dade2-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
