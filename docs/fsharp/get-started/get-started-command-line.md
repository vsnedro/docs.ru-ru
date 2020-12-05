---
title: 'Приступая к работе с F # с помощью программ командной строки'
description: 'Узнайте, как создать простое решение с несколькими проектами на F # с помощью .NET Core CLI в любой операционной системе (Windows, macOS или Linux).'
ms.date: 08/15/2020
ms.openlocfilehash: f890e31fe8c665874dc3034aebfae32e38b9031a
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739919"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Начало работы с F # с .NET Core CLI

В этой статье описывается, как можно приступить к работе с F # в любой операционной системе (Windows, macOS или Linux) с .NET Core CLI. Он проходит через создание многопроектного решения с библиотекой классов, которая вызывается консольным приложением.

## <a name="prerequisites"></a>Предварительные требования

Для начала необходимо установить последнюю [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

В этой статье предполагается, что вы умеете использовать командную строку и предпочитаемый текстовый редактор. Если вы еще не используете его, [Visual Studio Code](get-started-vscode.md) является отличным вариантом в качестве текстового редактора для F #.

## <a name="build-a-simple-multi-project-solution"></a>Создание простого решения с несколькими проектами

Откройте командную строку или терминал и выполните команду [DotNet New](../../core/tools/dotnet-new.md) , чтобы создать новый файл решения с именем `FSNetCore` :

```dotnetcli
dotnet new sln -o FSNetCore
```

Следующая структура каталогов создается после выполнения предыдущей команды:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Написание библиотеки классов

Перейдите в каталог *фснеткоре*.

Используйте `dotnet new` команду, чтобы создать проект библиотеки классов в папке **src** с именем Library.

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

Следующая структура каталогов создается после выполнения предыдущей команды:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Замените содержимое `Library.fs` следующим кодом:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    let json = JsonConvert.SerializeObject(value)
    $"I used to be {value} but now I'm {json} thanks to JSON.NET!"
```

Добавьте Newtonsoft.Jsв пакет NuGet в проект библиотеки.

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Добавьте `Library` проект в `FSNetCore` решение с помощью команды [DotNet SLN Add](../../core/tools/dotnet-sln.md) :

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

Выполните команду `dotnet build` , чтобы выполнить сборку проекта. При сборке будут восстановлены неразрешенные зависимости.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Написание консольного приложения, использующего библиотеку классов

Используйте `dotnet new` команду, чтобы создать консольное приложение в папке **src** с именем App.

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

Следующая структура каталогов создается после выполнения предыдущей команды:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Замените содержимое файла `Program.fs` приведенным ниже кодом.

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    for arg in argv do
        let value = getJsonNetJson arg
        printfn $"{value}"

    0 // return an integer exit code
```

Добавьте ссылку на `Library` проект с помощью команды [DotNet Add](../../core/tools/dotnet-add-reference.md).

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Добавьте `App` проект в `FSNetCore` решение с помощью `dotnet sln add` команды:

```dotnetcli
dotnet sln add src/App/App.fsproj
```

Чтобы выполнить сборку проекта, восстановите зависимости NuGet `dotnet restore` и выполните команду `dotnet build` .

Перейдите в каталог `src/App` консольного проекта и запустите проект, передавая `Hello World` в качестве аргументов:

```dotnetcli
cd src/App
dotnet run Hello World
```

Вы увидите следующие результаты:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Дальнейшие действия

Далее ознакомьтесь с [обзором f #](../tour.md) , чтобы узнать больше о различных функциях f #.
