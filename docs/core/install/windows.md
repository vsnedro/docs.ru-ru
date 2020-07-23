---
title: Установка .NET Core в Windows
description: Сведения о версиях Windows, в которых возможна установка .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/22/2020
ms.openlocfilehash: 97f67d00b3eb4dafc55256aea51f4295bb0ef06a
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308953"
---
# <a name="install-net-core-on-windows"></a>Установка .NET Core в Windows

> [!div class="op_single_selector"]
>
> - [Установка в Windows](windows.md)
> - [Установка в macOS](macos.md)
> - [Установка на Linux](linux.md)

В этой статье вы узнаете, как установить .NET Core в Windows. .NET Core состоит из среды выполнения и пакета SDK. Среда выполнения используется для запуска приложения .NET Core и может не включаться в состав приложения. Пакет SDK используется для создания приложений и библиотек .NET Core. Среда выполнения .NET Core всегда устанавливается вместе с пакетом SDK.

.NET Core 3.1 является последней версией.

> [!div class="button"]
> [Загрузить .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Поддерживаемые выпуски

В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Windows, в которых они поддерживаются. Эти версии поддерживаются до окончания поддержки версии [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), либо до окончания жизненного цикла версии [Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

Даты окончания жизненного цикла версий Windows 10 зависят от выпуска. В следующей таблице рассматриваются только выпуски **Домашняя**, **Профессиональная**, **Pro для образовательных учреждений** и **Pro для рабочих станций**. Дополнительные сведения см. в [справочных материалах по жизненному циклу поддержки Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

- Значок ✔️ означает, что версия Windows или .NET Core поддерживается.
- Значок ❌ означает, что версия Windows или версия .NET Core в таком выпуске Windows не поддерживается.
- Если значок ✔️ стоит как напротив версии Windows, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.

| Операционная система                      | .NET Core 2.1 | .NET Core 3.1 | Предварительная версия .NET 5 |
|-----------------------------|---------------|---------------|----------------|
| ✔️ Windows 10, версия 2004 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ✔️ Windows 10, версия 1909 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ✔️ Windows 10, версия 1903 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ✔️ Windows 10, версия 1809 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |
| ❌ Windows 10, версия 1803 | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |
| ❌ Windows 10, версия 1709 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |
| ❌ Windows 10, версия 1703 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |
| ❌ Windows 10, версия 1607 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |
| ❌ Windows 10, версия 1511 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |
| ❌ Windows 10, версия 1507 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (предварительная версия) |

## <a name="unsupported-releases"></a>Неподдерживаемые выпуски

Следующие версии .NET Core больше ❌ не поддерживаются (но остаются доступными для скачивания):

- 3.0
- 2.2
- 2.0

## <a name="runtime-information"></a>Сведения о среде выполнения

Среда выполнения используется для запуска приложений, созданных с помощью .NET Core. При публикации приложения автор может включить среду выполнения в его состав. В противном случае устанавливать среду выполнения будет пользователь.

В Windows можно установить три различные версии среды выполнения:

*Среда выполнения ASP.NET Core*\
Используется для запуска приложений ASP.NET Core. Включает среду выполнения .NET Core.

*Среда выполнения для классических приложений*\
Используется для запуска классических приложений .NET Core WPF и .NET Core Windows Forms для Windows. Включает среду выполнения .NET Core.

*Среда выполнения .NET Core*\
Простейшая среда выполнения, в состав которой не входят какие-либо другие среды выполнения. Чтобы обеспечить максимальный уровень совместимости с приложениями .NET Core, настоятельно рекомендуется устанавливать *среду выполнения ASP.NET Core* и *среду выполнения для классических приложений*.

> [!div class="button"]
> [Скачать среду выполнения .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Сведения о пакете SDK

Пакет SDK используется для создания и публикации приложений и библиотек .NET Core. При установке пакета SDK также устанавливаются все три [среды выполнения](#runtime-information): ASP.NET Core, среда выполнения для классических приложений и .NET Core.

> [!div class="button"]
> [Скачать пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>Зависимости

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 8.1                            | x64, x86        |
| Клиент Windows 10             | Версия 1609+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano Server                   | Версия 1803+                  | x64, ARM32      |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.1, см. в статье [Поддерживаемые .NET Core 3.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*Сейчас .NET Core 3.0 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 3.0 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano Server                   | Версия 1803+                  | x64, ARM32      |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.0, см. в статье [Поддерживаемые .NET Core 3.0 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*Сейчас .NET Core 2.2 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 2.2 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 с пакетом обновления 1 или более поздней версии (SP1+)                   | x64, x86        |
| Nano Server                   | Версия 1803+                   | x64, ARM32      |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.2, см. в статье [Поддерживаемые .NET Core 2.2 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 с пакетом обновления 1 или более поздней версии (SP1+)                   | x64, x86        |
| Nano Server                   | Версия 1803+                  | x64,            |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.1, см. в статье [Поддерживаемые .NET Core 2.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2

При установке пакета SDK для .NET или среды выполнения .NET в следующих версиях Windows требуются дополнительные зависимости:

- ❌ Windows 7 с пакетом обновления 1 (SP1)
- ❌ Windows Vista с пакетом обновления 2 (SP2)
- ✔️ Windows 8.1
- ✔️ Windows Server 2008 R2
- ✔️ Windows Server 2012 R2

Установите следующие компоненты:

- [Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

Приведенные выше требования также применяются, если возникает одна из следующих ошибок:

> Запуск программы невозможен, так как на компьютере отсутствует *api-ms-win-crt-runtime-l1-1-0.dll*. Попробуйте переустановить программу.
>
> \- или -
>
> Запуск программы невозможен, так как на компьютере отсутствует файл *api-ms-win-cor-timezone-l1-1-0.dll*. Попробуйте переустановить программу.
>
> \- или -
>
> Библиотека *hostfxr.dll* найдена, но при ее загрузке из *C:\\\<path_to_app>\\hostfxr.dll* произошел сбой.

## <a name="install-with-powershell-automation"></a>Установка с помощью функции автоматизации PowerShell

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации непрерывной интеграции и ее осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Вы можете выбрать конкретный выпуск, указав параметр `Channel`. Включите параметр `Runtime` для установки среды выполнения. В противном случае сценарий устанавливает пакет [SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

Установите пакет SDK, опустив параметр `-Runtime`. В этом примере для параметра `-Channel` задано значение `Current`, которое определяет установку последней поддерживаемой версии.

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a>Установка с помощью Visual Studio

Если вы используете Visual Studio для разработки приложений .NET Core, в следующей таблице указана минимальная требуемая версия Visual Studio на основе целевой версии пакета SDK для .NET Core.

| Версия пакета SDK для .NET Core | Версия Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 версии 16.4 или более поздней. |
| 3.0                   | Visual Studio 2019 версии 16.3 или более поздней. |
| 2.2                   | Visual Studio 2017 версии 15.9 или более поздней. |
| 2.1                   | Visual Studio 2017 версии 15.7 или более поздней. |

Если среда Visual Studio уже установлена, вы можете проверить ее версию, выполнив указанные ниже действия.

01. Запустите Visual Studio.
01. Выберите **Справка** > **О Microsoft Visual Studio**.
01. Считайте номер версии из диалогового окна **О программе**.

Visual Studio может установить последнюю пакета SDK для .NET Core и среды выполнения .NET Core.

> [!div class="button"]
> [Скачайте Visual Studio.](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

### <a name="select-a-workload"></a>Выбор рабочей нагрузки

При установке или изменении Visual Studio выберите одну или несколько из следующих рабочих нагрузок в зависимости от типа создаваемого приложения:

- рабочая нагрузка **Кроссплатформенная разработка .NET Core** в разделе **Другие наборы инструментов**;
- рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Веб-разработка и облако**;
- рабочая нагрузка **Разработка для Azure** в разделе **Веб-разработка и облако**;
- рабочая нагрузка **Разработка классических приложений .NET** в разделе **Классические и мобильные**.

[![Windows Visual Studio 2019 с рабочей нагрузкой .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Установка вместе с Visual Studio Code

Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере. Visual Studio Code доступен для Windows, macOS и Linux.

Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET Core, таким как Visual Studio, добавление поддержки .NET Core не вызывает затруднений.

01. [Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).
01. [Скачайте и установите пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
01. [Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="download-and-manually-install"></a>Скачивание и установка вручную

В качестве альтернативы установщикам Windows для .NET Core можно скачать и вручную установить пакет SDK или среду выполнения. Ручная установка как правило выполняется в рамках тестирования непрерывной интеграции. В большинстве случаев разработчикам и пользователям рекомендуется использовать [установщик](https://dotnet.microsoft.com/download/dotnet-core).

Как пакет SDK для .NET Core, так и среду выполнения .NET Core можно установить вручную после скачивания. При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения. Сначала скачайте двоичный выпуск пакета SDK или среды выполнения с одного из следующих сайтов:

- ✔️ [Предварительные версии скачиваемых файлов .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Скачиваемые файлы .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [Скачиваемые файлы .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Все скачиваемые файлы для .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Создайте каталог, в который будет выполнено извлечение .NET, например `%USERPROFILE%\dotnet`. Затем извлеките скачанный ZIP-файл в этот каталог.

По умолчанию команды и приложения .NET Core CLI не будут использовать платформу .NET Core, установленную таким образом. Вам нужно выбрать ее явно. Для этого измените переменные среды, с которыми запускается приложение:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

Такой подход позволяет установить несколько версий в отдельные расположения, а затем явно выбрать расположение установки, которое должно использовать приложение, запустив приложение с переменными среды, указывающими на это расположение.

Если параметр `DOTNET_MULTILEVEL_LOOKUP` имеет значение `0`, .NET Core игнорирует любые установленные глобально версии .NET Core. Если нужно, чтобы платформа .NET Core учитывала глобальное расположение установки по умолчанию при выборе лучшей платформы для запуска приложения, удалите этот параметр среды. По умолчанию обычно используется каталог `C:\Program Files\dotnet`, в который выполняется установка .NET Core при использовании установщика.

## <a name="docker"></a>Docker

Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы. Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.

.NET Core можно выполнять в контейнере Docker. Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/). Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.

Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев. Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.

Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Следующие шаги

- [Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md?pivots=os-windows).
- [Учебник. Hello World](../tutorials/with-visual-studio.md).
- [Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).
