---
title: Установка .NET Core в macOS
description: Сведения о версиях macOS, в которых возможна установка .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: 951e9b6a64d55274729e233b4a2d7728c75d05d4
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302936"
---
# <a name="install-net-core-on-macos"></a>Установка .NET Core в macOS

> [!div class="op_single_selector"]
>
> - [Установка в Windows](windows.md)
> - [Установка в macOS](macos.md)
> - [Установка на Linux](linux.md)

В этой статье вы узнаете, как установить .NET Core в macOS. .NET Core состоит из среды выполнения и пакета SDK. Среда выполнения используется для запуска приложения .NET Core и может не включаться в состав приложения. Пакет SDK используется для создания приложений и библиотек .NET Core. Среда выполнения .NET Core всегда устанавливается вместе с пакетом SDK.

.NET Core 3.1 является последней версией.

> [!div class="button"]
> [Загрузить .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Поддерживаемые выпуски

В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий macOS, в которых они поддерживаются. Эти версии будут поддерживаться до [окончания срока поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- Значок ✔️ означает, что версия .NET Core поддерживается.
- Значок ❌️ означает, что версия .NET Core не поддерживается.

| Операционная система          | .NET Core 2.1 | .NET Core 3.1 | Предварительная версия .NET 5 |
|---------------------------|---------------|---------------|----------------|
| macOS 10.15 "Catalina"    | ✔️ 2.1 ([заметки о выпуске][release-notes-21]) | ✔️ 3.1 ([заметки о выпуске][release-notes-31]) | ✔️ 5.0, предварительная версия ([заметки о выпуске][release-notes-50]) |
| macOS 10.14 "Mojave"      | ✔️ 2.1 ([заметки о выпуске][release-notes-21]) | ✔️ 3.1 ([заметки о выпуске][release-notes-31]) | ✔️ 5.0, предварительная версия ([заметки о выпуске][release-notes-50]) |
| macOS 10.13 "High Sierra" | ✔️ 2.1 ([заметки о выпуске][release-notes-21]) | ✔️ 3.1 ([заметки о выпуске][release-notes-31]) | ✔️ 5.0, предварительная версия ([заметки о выпуске][release-notes-50]) |
| macOS 10.12 "Sierra"      | ✔️ 2.1 ([заметки о выпуске][release-notes-21]) | ❌ 3.1 ([заметки о выпуске][release-notes-31]) | ❌ 5.0, предварительная версия ([заметки о выпуске][release-notes-50]) |

## <a name="unsupported-releases"></a>Неподдерживаемые выпуски

Следующие версии .NET Core больше ❌ не поддерживаются (но остаются доступными для скачивания):

- 3.0 ([заметки о выпуске][release-notes-30])
- 2.2 ([заметки о выпуске][release-notes-22])
- 2.0 ([заметки о выпуске][release-notes-20])

## <a name="runtime-information"></a>Сведения о среде выполнения

Среда выполнения используется для запуска приложений, созданных с помощью .NET Core. При публикации приложения автор может включить среду выполнения в его состав. В противном случае устанавливать среду выполнения будет пользователь.

В macOS можно установить три различные версии среды выполнения:

*Среда выполнения ASP.NET Core*\
Используется для запуска приложений ASP.NET Core. Включает среду выполнения .NET Core.

*Среда выполнения .NET Core*\
Простейшая среда выполнения, в состав которой не входят какие-либо другие среды выполнения. Чтобы обеспечить максимальный уровень совместимости с приложениями .NET Core, настоятельно рекомендуется устанавливать *среду выполнения ASP.NET Core*.

> [!div class="button"]
> [Скачать среду выполнения .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Сведения о пакете SDK

Пакет SDK используется для создания и публикации приложений и библиотек .NET Core. При установке пакета SDK также устанавливаются обе [среды выполнения](#runtime-information): ASP.NET Core и .NET Core.

> [!div class="button"]
> [Скачать пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>Зависимости

Платформа .NET Core поддерживается в следующих выпусках macOS:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Версия .NET Core | macOS                 | Архитектуры |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13+)  | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13+)  | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12+)       | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12+)       | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

Начиная с macOS Catalina (версия 10.15) все программное обеспечение, созданное после 1 июня 2019 года и распространяемое с идентификатором разработчика, должно быть заверено. Это требование относится к среде выполнения .NET Core, пакету SDK для .NET Core и программному обеспечению, созданному с помощью .NET Core.

Установщики для .NET Core (среда выполнения и пакет SDK) версии 3.1, 3.0 и 2.1 были заверены с 18 февраля 2020 г. Более ранние версии не заверены. При запуске незаверенного приложения появится ошибка, аналогичная следующей:

![Оповещение о заверении macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

Дополнительные сведения о том, как принудительное заверение влияет на .NET Core (и ваши приложения .NET Core), см. в разделе [Работа с заверением macOS Catalina](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Приложения .NET Core, которые используют сборку *System.Drawing.Common*, требуют установки libgdiplus.

Легко получить libgdiplus можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS. После установки *brew* установите libgdiplus, выполнив следующие команды в окне терминала (аналог командной строки):

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a>Установка с помощью установщика

В macOS есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:

- [Процессоры x64 (64-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Скачивание и установка вручную

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

В качестве альтернативы установщикам macOS для .NET Core можно скачать и вручную установить пакет SDK и среду выполнения. Ручная установка как правило выполняется в рамках тестирования непрерывной интеграции. В большинстве случаев разработчикам и пользователям рекомендуется использовать [установщик](https://dotnet.microsoft.com/download/dotnet-core).

При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения. Сначала скачайте **двоичный** выпуск пакета SDK или среды выполнения с одного из следующих сайтов:

- ✔️ [Предварительные версии скачиваемых файлов .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Скачиваемые файлы .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [Скачиваемые файлы .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Все скачиваемые файлы для .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Извлеките скачанный файл и используйте команду `export`, чтобы задать переменные, используемые .NET Core, а затем проверьте включение .NET Core в переменную PATH.

Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала скачайте двоичный выпуск .NET Core. Затем откройте терминал и выполните следующие команды в каталоге с сохраненным файлом. Имя файла архива может отличаться в зависимости от скачанных файлов.

**Извлеките среду выполнения, используя следующую команду**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Извлеките пакет SDK, используя следующую команду**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Приведенные выше команды `export` сделают команды .NET Core CLI доступными только для сеанса терминала, в котором производился запуск.
>
> Вы можете изменить профиль оболочки, чтобы добавить команды окончательно. Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль. Пример:
>
> - **Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*
> - **Оболочка Korn**: *~/.kshrc* или *.profile*
> - **Оболочка Z**: *~/.zshrc* или *.zprofile*
>
> Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`. Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.
>
> Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.

Такой подход позволяет устанавливать разные версии в отдельные расположения и выбирать, какие из них следует использовать для каждого приложения.

## <a name="install-with-visual-studio-for-mac"></a>Установка с помощью Visual Studio для Mac

Visual Studio для Mac устанавливает пакет SDK для .NET Core, если выбрана рабочая нагрузка **.NET Core**. Чтобы приступить к разработке в .NET Core на macOS, ознакомьтесь со статьей [Установка Visual Studio 2019 для Mac](/visualstudio/mac/installation). В последнем выпуске .NET Core 3.1 необходимо использовать предварительную версию Visual Studio для Mac 8.4.

[![Visual Studio 2019 для Mac с компонентом рабочей нагрузки .NET Core в macOS](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Установка вместе с Visual Studio Code

Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере. Visual Studio Code доступен для Windows, macOS и Linux.

Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET Core, таким как Visual Studio, добавление поддержки .NET Core не вызывает затруднений.

01. [Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).
01. [Скачайте и установите пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
01. [Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="install-with-bash-automation"></a>Установка с помощью функции автоматизации Bash

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Вы можете выбрать конкретный выпуск, указав параметр `current`. Включите параметр `runtime` для установки среды выполнения. В противном случае сценарий устанавливает пакет [SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости. Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.

## <a name="docker"></a>Docker

Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы. Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.

.NET Core можно выполнять в контейнере Docker. Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/). Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.

Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев. Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.

Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Следующие шаги

- [Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md?pivots=os-macos).
- [Работа с заверением macOS Catalina](macos-notarization-issues.md).
- [Учебник. Начало работы с macOS](../tutorials/with-visual-studio-mac.md).
- [Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
