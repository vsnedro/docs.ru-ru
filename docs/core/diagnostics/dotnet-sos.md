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
# <a name="sos-installer-dotnet-sos"></a>Установщик SOS (dotnet-sos)

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="install"></a>Установка

Есть два способа загрузки и установки `dotnet-sos`:

- **Средство dotnet global:**

  Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- **Прямое скачивание:**

  скачайте исполняемый файл средства, соответствующий вашей платформе:

  | OS  | Платформа |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-sos/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64) |

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
