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
# <a name="sos-installer-dotnet-sos"></a>Установщик SOS (dotnet-sos)

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="install-dotnet-sos"></a>Установка dotnet-sos

Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Описание

Глобальное средство `dotnet-sos` устанавливает [расширение отладчика SOS](../../framework/tools/sos-dll-sos-debugging-extension.md), которое позволяет выполнять [проверку управляемого состояния .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) из собственных отладчиков, таких как WinDbg/CDB в Windows и lldb в Linux и macOS. Последние версии отладчика Windows (> = версия 10.0.18317.1001 WinDbg или CDB) загружают SOS автоматически из коллекции расширений Майкрософт, поэтому установка SOS через средство `dotnet-sos` требуется только в Linux и macOS или при использовании в Windows старых средств отладки.

## <a name="options"></a>Параметры

- **`--version`**

  Отображение сведений о версии.

- **`-h|--help`**

  Отображение справки в командной строке.

## <a name="dotnet-sos-install"></a>dotnet-sos install

Установка [расширения SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) локально для отладки процессов .NET Core. В macOS и Linux файл LLDBINIT будет обновлен таким образом, чтобы расширение загружалось автоматически при запуске lldb. При установке SOS в Windows с более старыми средствами отладки (< версии 10.0.18317.1001) необходимо вручную загрузить расширение в WinDbg или CDB, запустив `.load %USERPROFILE%\.dotnet\sos\sos.dll` в отладчике.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>dotnet-sos uninstall

Удаление [расширения SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) и, если в Linux или macOS, удаление из конфигурации lldb.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-sos uninstall
```
