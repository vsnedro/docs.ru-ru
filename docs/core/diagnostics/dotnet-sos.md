---
title: Средство диагностики dotnet-sos — .NET CLI
description: Узнайте, как установить и использовать средство CLI dotnet-sos для управления расширением отладчика SOS, которое используется с собственными отладчиками в Windows и Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825446"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="23fe1-103">Установщик SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="23fe1-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="23fe1-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="23fe1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="23fe1-105">Установка</span><span class="sxs-lookup"><span data-stu-id="23fe1-105">Install</span></span>

<span data-ttu-id="23fe1-106">Есть два способа загрузки и установки `dotnet-sos`:</span><span class="sxs-lookup"><span data-stu-id="23fe1-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="23fe1-107">**Средство dotnet global:**</span><span class="sxs-lookup"><span data-stu-id="23fe1-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="23fe1-108">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="23fe1-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="23fe1-109">**Прямое скачивание:**</span><span class="sxs-lookup"><span data-stu-id="23fe1-109">**Direct download:**</span></span>

  <span data-ttu-id="23fe1-110">скачайте исполняемый файл средства, соответствующий вашей платформе:</span><span class="sxs-lookup"><span data-stu-id="23fe1-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="23fe1-111">OS</span><span class="sxs-lookup"><span data-stu-id="23fe1-111">OS</span></span>  | <span data-ttu-id="23fe1-112">Платформа</span><span class="sxs-lookup"><span data-stu-id="23fe1-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="23fe1-113">Windows</span><span class="sxs-lookup"><span data-stu-id="23fe1-113">Windows</span></span> | <span data-ttu-id="23fe1-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="23fe1-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="23fe1-115">macOS</span><span class="sxs-lookup"><span data-stu-id="23fe1-115">macOS</span></span>   | [<span data-ttu-id="23fe1-116">x64</span><span class="sxs-lookup"><span data-stu-id="23fe1-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="23fe1-117">Linux</span><span class="sxs-lookup"><span data-stu-id="23fe1-117">Linux</span></span>   | <span data-ttu-id="23fe1-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="23fe1-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="23fe1-119">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="23fe1-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="23fe1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="23fe1-120">Description</span></span>

<span data-ttu-id="23fe1-121">Глобальное средство `dotnet-sos` устанавливает [расширение отладчика SOS](../../framework/tools/sos-dll-sos-debugging-extension.md), которое позволяет выполнять [проверку управляемого состояния .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) из собственных отладчиков, таких как WinDbg/CDB в Windows и lldb в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="23fe1-121">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="23fe1-122">Последние версии отладчика Windows (> = версия 10.0.18317.1001 WinDbg или CDB) загружают SOS автоматически из коллекции расширений Майкрософт, поэтому установка SOS через средство `dotnet-sos` требуется только в Linux и macOS или при использовании в Windows старых средств отладки.</span><span class="sxs-lookup"><span data-stu-id="23fe1-122">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="23fe1-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="23fe1-123">Options</span></span>

- **`--version`**

  <span data-ttu-id="23fe1-124">Отображение сведений о версии.</span><span class="sxs-lookup"><span data-stu-id="23fe1-124">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="23fe1-125">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="23fe1-125">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="23fe1-126">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="23fe1-126">dotnet-sos install</span></span>

<span data-ttu-id="23fe1-127">Установка [расширения SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) локально для отладки процессов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="23fe1-127">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="23fe1-128">В macOS и Linux файл LLDBINIT будет обновлен таким образом, чтобы расширение загружалось автоматически при запуске lldb.</span><span class="sxs-lookup"><span data-stu-id="23fe1-128">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="23fe1-129">При установке SOS в Windows с более старыми средствами отладки (< версии 10.0.18317.1001) необходимо вручную загрузить расширение в WinDbg или CDB, запустив `.load %USERPROFILE%\.dotnet\sos\sos.dll` в отладчике.</span><span class="sxs-lookup"><span data-stu-id="23fe1-129">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="23fe1-130">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="23fe1-130">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="23fe1-131">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="23fe1-131">dotnet-sos uninstall</span></span>

<span data-ttu-id="23fe1-132">Удаление [расширения SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) и, если в Linux или macOS, удаление из конфигурации lldb.</span><span class="sxs-lookup"><span data-stu-id="23fe1-132">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="23fe1-133">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="23fe1-133">Synopsis</span></span>

```console
dotnet-sos uninstall
```
