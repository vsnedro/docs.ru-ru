---
title: dotnet-sos — .NET Core
description: Сведения о том, как установить и использовать программу командной строки dotnet-sos.
ms.date: 08/26/2020
ms.openlocfilehash: ba83105718909038ca56129ed8a5063aeff12e89
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065088"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="3dcd1-103">Установщик SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="3dcd1-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="3dcd1-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="3dcd1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-sos"></a><span data-ttu-id="3dcd1-105">Установка dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="3dcd1-105">Install dotnet-sos</span></span>

<span data-ttu-id="3dcd1-106">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="3dcd1-106">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a><span data-ttu-id="3dcd1-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3dcd1-107">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="3dcd1-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3dcd1-108">Description</span></span>

<span data-ttu-id="3dcd1-109">Глобальное средство `dotnet-sos` устанавливает [расширение отладчика SOS](../../framework/tools/sos-dll-sos-debugging-extension.md), которое позволяет выполнять [проверку управляемого состояния .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) из собственных отладчиков, таких как WinDbg/CDB в Windows и lldb в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-109">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="3dcd1-110">Последние версии отладчика Windows (> = версия 10.0.18317.1001 WinDbg или CDB) загружают SOS автоматически из коллекции расширений Майкрософт, поэтому установка SOS через средство `dotnet-sos` требуется только в Linux и macOS или при использовании в Windows старых средств отладки.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-110">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="3dcd1-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="3dcd1-111">Options</span></span>

- **`--version`**

  <span data-ttu-id="3dcd1-112">Отображение сведений о версии.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-112">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3dcd1-113">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-113">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="3dcd1-114">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="3dcd1-114">dotnet-sos install</span></span>

<span data-ttu-id="3dcd1-115">Установка [расширения SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) локально для отладки процессов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-115">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="3dcd1-116">В macOS и Linux файл LLDBINIT будет обновлен таким образом, чтобы расширение загружалось автоматически при запуске lldb.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-116">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="3dcd1-117">При установке SOS в Windows с более старыми средствами отладки (< версии 10.0.18317.1001) необходимо вручную загрузить расширение в WinDbg или CDB, запустив `.load %USERPROFILE%\.dotnet\sos\sos.dll` в отладчике.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-117">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3dcd1-118">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3dcd1-118">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="3dcd1-119">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="3dcd1-119">dotnet-sos uninstall</span></span>

<span data-ttu-id="3dcd1-120">Удаление [расширения SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) и, если в Linux или macOS, удаление из конфигурации lldb.</span><span class="sxs-lookup"><span data-stu-id="3dcd1-120">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3dcd1-121">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3dcd1-121">Synopsis</span></span>

```console
dotnet-sos uninstall
```
