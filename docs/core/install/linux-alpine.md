---
title: Установка .NET в Alpine — .NET
description: Здесь приводятся различные способы установки пакета SDK для .NET и среды выполнения .NET в Alpine.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506835"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Установка пакета SDK для .NET или среды выполнения .NET в Alpine

В этой статье описано, как установить .NET в Alpine. Если поддержка какой-либо версии Alpine прекращается, то .NET также перестает поддерживать ее. Но с помощью этих инструкций вы сможете запустить .NET даже в неподдерживаемых версиях.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Установщиков для Alpine не существует. Необходимо либо использовать [сценарий установки](#scripted-install), либо следовать инструкциям по [установке вручную](#manual-install).

## <a name="supported-distributions"></a>Поддерживаемые дистрибутивы

В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET и версий Alpine, в которых они поддерживаются. Эти версии поддерживаются до окончания поддержки версии [.NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) либо до окончания жизненного цикла версии [Alpine](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- Значок ✔️ означает, что версия Alpine или .NET поддерживается.
- Значок ❌ означает, что версия Alpine или версия .NET в таком выпуске Alpine не поддерживается.
- Если значок ✔️ стоит как напротив версии Alpine, так и напротив версии .NET, это значит, что такое сочетание ОС и .NET поддерживается.

| Alpine  | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|-------- |---------------|---------------|----------------|
| ✔️ 3.12 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.11 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.10 | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.9  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.8  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |

Следующие версии .NET больше не поддерживаются. (но остаются доступными для скачивания):

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Зависимости

Для .NET в Alpine Linux необходимо установить следующие зависимости:

- icu-libs
- krb5-libs
- libgcc
- libintl
- libssl 1.1 (Alpine версии 3.9 или более поздней)
- libssl1.0 (Alpine версии 3.8 или более ранней)
- libstdc++
- zlib

## <a name="scripted-install"></a>Установка с помощью сценария

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Установка вручную

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Следующие шаги

- [Учебник. Создание консольного приложения с помощью пакета SDK для .NET в Visual Studio Code](../tutorials/with-visual-studio-code.md)
