---
title: Начало работы с .NET
description: Создание приложения .NET "Hello World".
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756095"
---
# <a name="get-started-with-net"></a>Начало работы с .NET

В этой статье объясняется, как создать и запустить приложение .NET "Hello World!".

Если вы не знаете, что такое .NET, начните с раздела о [знакомстве с .NET](introduction.md).

## <a name="create-an-application"></a>Создание приложения

Сначала скачайте и установите [пакет SDK для .NET](https://dotnet.microsoft.com/download/dotnet-core) на компьютер.

Затем откройте окно терминала, например **PowerShell**, **командную строку** или **bash**. Для создания и запуска приложения C# введите следующие команды `dotnet`:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Вы увидите такой результат:

```output
Hello World!
```

Поздравляем! Вы создали простое приложение .NET.

## <a name="next-steps"></a>Дальнейшие действия

Начните разработку приложений .NET со знакомства с [пошаговым руководством](../standard/get-started.md) или с просмотра [видеороликов о .NET](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) на YouTube.
