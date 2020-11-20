---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634472"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="430e6-103">Справочник по команде dotnet help</span><span class="sxs-lookup"><span data-stu-id="430e6-103">dotnet help reference</span></span>

<span data-ttu-id="430e6-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="430e6-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="430e6-105">Имя</span><span class="sxs-lookup"><span data-stu-id="430e6-105">Name</span></span>

<span data-ttu-id="430e6-106">`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="430e6-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="430e6-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="430e6-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="430e6-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="430e6-108">Description</span></span>

<span data-ttu-id="430e6-109">Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="430e6-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="430e6-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="430e6-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="430e6-111">Имя команды интерфейса командной строки .NET.</span><span class="sxs-lookup"><span data-stu-id="430e6-111">Name of the .NET CLI command.</span></span> <span data-ttu-id="430e6-112">Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="430e6-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="430e6-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="430e6-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="430e6-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="430e6-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="430e6-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="430e6-115">Examples</span></span>

- <span data-ttu-id="430e6-116">Открывает страницу документации по команде[dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="430e6-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
