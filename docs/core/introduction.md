---
title: Введение в .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и macOS. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: f99b446bbd38b2b814c13afa13ab34cd5c9aa086
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645526"
---
# <a name="introduction-to-net-core"></a>Введение в .NET Core

[.NET Core](about.md) — это платформа разработки общего назначения с [открытым кодом](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), предназначенная для создания кроссплатформенных приложений. Вы можете создавать приложения .NET Core для Windows, macOS и Linux с поддержкой процессоров x64, x86, ARM32 и ARM64, используя несколько языков программирования. Вам доступны платформы и API-интерфейсы для создания [облачных](/aspnet/core/) приложений, приложений для [Интернета вещей](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), использования [клиентского интерфейса](../desktop-wpf/overview/index.md) и [машинного обучения](/dotnet/machine-learning/).

Скачайте [пакет SDK для .NET Core](https://dotnet.microsoft.com/download), чтобы поработать с .NET Core на компьютере. [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/) является последней версией.

## <a name="download-net-core"></a>Скачать .NET Core

.NET Core можно получить следующими способами.

* [Установщики для Windows и macOS](https://dotnet.microsoft.com/download)
* [Пакеты Linux](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [Контейнеры Docker](https://hub.docker.com/_/microsoft-dotnet-core/)
* [ZIP- и TAR-архивы](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [Скрипты установки](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [Заметки о выпуске](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a>Создание первого приложения

После установки пакета SDK для .NET Core откройте командную строку. Для создания и запуска приложения используйте следующие команды.

```dotnetcli
dotnet new console
dotnet run
```

Должны выводиться следующие данные:

```output
Hello World!
```

## <a name="contribute"></a>Участие

.NET Core является открытой платформа. Участвовать в разработке может любой желающий.

* Проблемы и вопросы можно размещать в [Сообществе разработчиков](https://developercommunity.visualstudio.com/spaces/61/index.html).
* Дополнения по продуктам следует вносить в один из репозиториев проекта, например [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) или [aspnetcore](https://github.com/dotnet/aspnetcore). Дополнительные сведения см. в статье [Репозитории .NET Core](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).

## <a name="support"></a>Поддержка

Корпорация Майкрософт обеспечивает поддержку .NET Core в Windows, macOS, Linux, а компания Red Hat — в Red Hat Enterprise Linux.

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Учебники по .NET Core](tutorials/index.md)

> [!div class="nextstepaction"]
> [Работа с .NET Core в браузере](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
