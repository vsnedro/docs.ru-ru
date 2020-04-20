---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 02/14/2020
ms.openlocfilehash: a59e74a318118b6fd39d1895df02d76daa6fc9e1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463688"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="e632d-103">Справочник по команде dotnet help</span><span class="sxs-lookup"><span data-stu-id="e632d-103">dotnet help reference</span></span>

<span data-ttu-id="e632d-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e632d-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e632d-105">Имя</span><span class="sxs-lookup"><span data-stu-id="e632d-105">Name</span></span>

<span data-ttu-id="e632d-106">`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="e632d-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e632d-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e632d-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="e632d-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="e632d-108">Description</span></span>

<span data-ttu-id="e632d-109">Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="e632d-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="e632d-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e632d-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="e632d-111">Имя команды интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e632d-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="e632d-112">Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="e632d-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="e632d-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="e632d-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="e632d-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e632d-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="e632d-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="e632d-115">Examples</span></span>

- <span data-ttu-id="e632d-116">Открывает страницу документации по команде[dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="e632d-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
