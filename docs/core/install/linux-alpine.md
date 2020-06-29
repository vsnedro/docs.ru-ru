---
title: Установка .NET Core в Alpine — .NET Core
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Alpine.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324836"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a>Установка пакета SDK для .NET Core или среды выполнения .NET Core в Alpine

В этой статье описано, как установить .NET Core в Alpine. Если поддержка какой-либо версии Alpine прекращается, то .NET Core также перестает поддерживать ее. Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Установщиков для Alpine не существует. Необходимо либо использовать [сценарий установки](#scripted-install), либо следовать инструкциям по [установке вручную](#manual-install).

## <a name="supported-distributions"></a>Поддерживаемые дистрибутивы

В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Alpine, в которых они поддерживаются. Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Alpine](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- Значок ✔️ означает, что версия Alpine или .NET Core поддерживается.
- Значок ❌ означает, что версия Alpine или версия .NET Core в таком выпуске Alpine не поддерживается.
- Если значок ✔️ стоит как напротив версии Alpine, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.

| Alpine                   | .NET Core 2.1 | .NET Core 3.1 | Предварительная версия .NET 5 |
|--------------------------|---------------|---------------|----------------|
| ✔️ 3.12  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ✔️ 3.11  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ✔️ 3.10  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ✔️ 3.9   | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ❌ 3.8   | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |

Следующие версии .NET Core больше не поддерживаются, (но остаются доступными для скачивания):

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Зависимости

Для .NET Core в Alpine Linux необходимо установить следующие зависимости:

- icu-libs
- krb5-libs
- libintl
- libssl 1.1 (Alpine версии 3.9 или более поздней)
- libssl 1.0 (Alpine версии 3.8)
- libstdc++
- lttng-ust
- numactl (необязательно)
- zlib

## <a name="scripted-install"></a>Установка с помощью сценария

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Установка вручную

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Следующие шаги

- [Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code](../tutorials/with-visual-studio-code.md)
