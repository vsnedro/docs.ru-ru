---
title: Начало работы с .NET Core
description: Ресурсы, посвященные созданию приложений .NET Core в Windows, Linux и macOS.
author: adegeo
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ddbee0764897b511cac0c4142354ba995d94a2b6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416062"
---
# <a name="get-started-with-net-core"></a>Начало работы с .NET Core

В этой статье представлены сведения по началу работы с .NET Core. .NET Core можно установить в Windows, Linux и macOS. Вы можете писать код в любом текстовом редакторе, а также создавать кроссплатформенные библиотеки и приложения.

Если вы не знаете, что такое .NET Core и как это связано с другими технологиями .NET, начните с обзора [Что такое .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet). Простыми словами, .NET Core — это кроссплатформенная реализация .NET с открытым исходным кодом.

## <a name="create-an-application"></a>Создание приложения

Сначала скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) на компьютер.

Затем откройте окно терминала, например **PowerShell**, **командную строку** или **bash**. Для создания и запуска приложения C# введите следующие команды `dotnet`:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Должны выводиться следующие данные:

```console
Hello World!
```

Поздравляем! Вы создали простое приложение .NET Core. Вы также можете использовать [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (только для Windows) или [Visual Studio для Mac](./tutorials/using-on-mac-vs.md) (только для macOS), чтобы создать приложение .NET Core.

## <a name="tutorials"></a>Учебники

Начало работы с разработкой приложений .NET Core, используя следующие пошаговые руководства.

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

- [Создание первого консольного приложения .NET Core в Visual Studio 2019](./tutorials/with-visual-studio.md)
- [Создание библиотеки классов с помощью .NET Standard в Visual Studio](./tutorials/library-with-visual-studio.md)
- [Начало работы с .NET Core с использованием .NET Core CLI](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![значок камеры для видеоролика](./media/video-icon.png "Посмотрите видео") | Посмотрите видео о том, [как установить и использовать Visual Studio Code и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) на канале Channel 9. |
| ![значок камеры для видеоролика](./media/video-icon.png "Посмотрите видео") | Просмотрите видео о [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) на YouTube. |

Список поддерживаемых версий Windows см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-windows).

# <a name="linux"></a>[Linux](#tab/linux)

Начало работы с разработкой приложений .NET Core, используя следующие пошаговые руководства.

- [Начало работы с .NET Core с помощью командной строки.](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![значок камеры для видеоролика](./media/video-icon.png "Посмотрите видео") | Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu). |

Список поддерживаемых дистрибутивов и версий Linux см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-linux).

# <a name="macos"></a>[macOS](#tab/macos)

Начало работы с разработкой приложений .NET Core, используя следующие пошаговые руководства.

- [Начало работы с .NET Core в macOS с помощью Visual Studio Code](./tutorials/using-on-macos.md)
- [Начало работы с .NET Core с помощью командной строки.](./tutorials/cli-create-console-app.md)
- [Начало работы с .NET Core в macOS с помощью Visual Studio для Mac](./tutorials/using-on-mac-vs.md)
- [Создание библиотеки .NET Standard в macOS с помощью Visual Studio для Mac](tutorials/library-with-visual-studio-mac.md)

|   |   |
|---|---|
| ![значок камеры для видеоролика](media/video-icon.png "Посмотрите видео") | Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac). |

Список поддерживаемых версий OS X и macOS см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-macos).

---
