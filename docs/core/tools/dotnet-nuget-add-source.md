---
title: Команда dotnet nuget add source
description: Команда dotnet nuget add source добавляет новый источник пакета в файлы конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 319501e026f1c3102006b0be5357f127b8e366a7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463591"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="cb7bb-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="cb7bb-103">dotnet nuget add source</span></span>

<span data-ttu-id="cb7bb-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="cb7bb-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cb7bb-105">name</span><span class="sxs-lookup"><span data-stu-id="cb7bb-105">Name</span></span>

<span data-ttu-id="cb7bb-106">`dotnet nuget add source` — добавляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb7bb-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cb7bb-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a><span data-ttu-id="cb7bb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cb7bb-108">Description</span></span>

<span data-ttu-id="cb7bb-109">Команда `dotnet nuget add source` добавляет новый источник пакета в файлы конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="cb7bb-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cb7bb-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="cb7bb-111">Путь к источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="cb7bb-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb7bb-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="cb7bb-113">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-113">The NuGet configuration file.</span></span> <span data-ttu-id="cb7bb-114">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="cb7bb-115">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="cb7bb-116">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="cb7bb-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name <SOURCE_NAME>`**

  <span data-ttu-id="cb7bb-117">Имя источника.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-117">Name of the source.</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="cb7bb-118">Пароль, используемый при подключении к источнику, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="cb7bb-119">Включает сохранение учетных данных переносимого источника пакетов путем отключения шифрования паролей.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="cb7bb-120">Имя пользователя, используемое при подключении к источнику, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="cb7bb-121">Разделенный запятыми список допустимых типов проверки подлинности для этого источника.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="cb7bb-122">Задайте значение `basic`, если сервер объявляет NTLM или Negotiate. Ваши учетные данные следует отправлять с помощью базового механизма, например, при использовании PAT с локальным Azure DevOps Server.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="cb7bb-123">К другим допустимым значениям относятся `negotiate`, `kerberos`, `ntlm` и `digest`, но они вряд ли будут полезны.</span><span class="sxs-lookup"><span data-stu-id="cb7bb-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="cb7bb-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="cb7bb-124">Examples</span></span>

- <span data-ttu-id="cb7bb-125">Добавьте `nuget.org` в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="cb7bb-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="cb7bb-126">Добавьте `c:\packages` в качестве локального источника:</span><span class="sxs-lookup"><span data-stu-id="cb7bb-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="cb7bb-127">Добавьте источник, требующий проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="cb7bb-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="cb7bb-128">Добавьте источник, требующий проверки подлинности (затем установите поставщик учетных данных):</span><span class="sxs-lookup"><span data-stu-id="cb7bb-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="cb7bb-129">См. также</span><span class="sxs-lookup"><span data-stu-id="cb7bb-129">See also</span></span>

- [<span data-ttu-id="cb7bb-130">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="cb7bb-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="cb7bb-131">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="cb7bb-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
