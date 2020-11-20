---
title: Проверка установленных версий .NET в Windows, Linux и macOS — .NET
description: Сведения о том, какие версии .NET установлены на компьютере. Сюда входит среда выполнения .NET и пакет SDK для .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d924e5bc58052cd760f367e906666d68ab79b764
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507219"
---
# <a name="how-to-check-that-net-is-already-installed"></a>Проверка того, установлена ли платформа .NET

Эта статья описывает, как проверить, какие версии среды выполнения .NET и пакета SDK установлены на компьютере. Возможно, платформа .NET уже установлена, если у вас есть интегрированная среда разработки, такая как Visual Studio или Visual Studio для Mac.

При установке пакета SDK устанавливается и соответствующая среда выполнения.

Если любая команда из этой статьи завершается ошибкой, среда выполнения или пакет SDK не установлены. Дополнительные сведения см. в статьях, посвященных установке в [Windows](windows.md), [macOS](macos.md) или [Linux](linux.md).

## <a name="check-sdk-versions"></a>Проверка версий пакета SDK

Вы можете узнать, какие версии пакета SDK для .NET установлены, с помощью терминала. Откройте терминал и выполните приведенную ниже команду.

```dotnetcli
dotnet --list-sdks
```

Вы получите результат, аналогичный приведенному ниже.

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
5.0.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
5.0.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
5.0.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a>Проверка версий среды выполнения

Вы можете узнать, какие версии среды выполнения .NET установлены, с помощью приведенной ниже команды.

```dotnetcli
dotnet --list-runtimes
```

Вы получите результат, аналогичный приведенному ниже.

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a>Проверка папок установки

Возможно, платформа .NET установлена, но не добавлена в переменную `PATH` для профиля операционной системы или пользователя. Выполнение команд из предыдущих разделов может не работать. В качестве альтернативы можно проверить существование папок установки .NET.

При установке с помощью установщика или сценария .NET устанавливается в стандартную папку. В большинстве случаев установщик или сценарий, который вы используете для установки .NET, предоставляет возможность установки в другую папку. Если вы решили выполнить установить в другую папку, измените начало пути к папке.

::: zone pivot="os-windows"

- **Исполняемый файл dotnet**\
_C:\\program files\\dotnet\\dotnet.exe_

- **Пакет SDK для .NET**\
_C:\\program files\\dotnet\\sdk\\{версия}\\_

- **Среда выполнения .NET**\
_C:\\program files\\dotnet\\shared\\{тип среды выполнения}\\{версия}\\_

::: zone-end

::: zone pivot="os-linux"

- **Исполняемый файл dotnet**\
_/home/user/share/dotnet/dotnet_

- **Пакет SDK для .NET**\
_/home/user/share/dotnet/sdk/{version}/_

- **Среда выполнения .NET**\
_/home/user/share/dotnet/shared/{тип среды выполнения}/{версия}/_

::: zone-end

::: zone pivot="os-macos"

- **Исполняемый файл dotnet**\
_/usr/local/share/dotnet/dotnet_

- **Пакет SDK для .NET**\
_/usr/local/share/dotnet/sdk/{версия}/_

- **Среда выполнения .NET**\
_/usr/local/share/dotnet/shared/{тип среды выполнения}/{версия}/_

::: zone-end

## <a name="more-information"></a>Дополнительные сведения

Версии пакета SDK и среды выполнения можно просмотреть с помощью команды `dotnet --info`. Вы также получите другие сведения о среде, такие как версия операционной системы и идентификатор среды выполнения (RID).

## <a name="next-steps"></a>Следующие шаги

- [Установка среды выполнения .NET и пакета SDK для Windows](windows.md).
- [Установка среды выполнения .NET и пакета SDK для MacOS](linux.md).
- [Установка среды выполнения .NET и пакета SDK для Linux](macos.md).
