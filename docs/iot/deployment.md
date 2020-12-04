---
title: Развертывание приложений .NET в Raspberry Pi
description: Узнайте, как развертывать приложения .NET на Raspberry Pi.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594128"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a>Развертывание приложений .NET в Raspberry Pi

Развертывание приложений .NET в Raspberry Pi идентично тому, что и любая другая платформа. Приложение может работать как *автономный* или *зависящий от платформы* режим развертывания. Каждая стратегия имеет свои преимущества. Дополнительные сведения см. в статье [Общие сведения о публикации приложений .NET](../core/deploying/index.md).

## <a name="deploying-a-framework-dependent-app"></a>Развертывание приложения, зависящего от платформы

Чтобы развернуть приложение как приложение, зависящее от платформы, выполните следующие действия.

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. Установите .NET на Raspberry Pi с помощью [скриптов DotNet-Install](../core/tools/dotnet-install-script.md). Выполните следующие действия из командной строки bash на устройстве Raspberry Pi (локальная или SSH):
    1. Выполните следующую команду, чтобы установить .NET:

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > При этом устанавливается последняя версия. Если требуется определенная версия, добавьте `--version <VERSION>` в конец, где `<VERSION>` — это конкретная версия сборки.

    1. Чтобы упростить разрешение пути, добавьте `DOTNET_ROOT` переменную среды и добавьте к ней каталог *. DotNet* `$PATH` с помощью следующих команд:

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. Проверьте установку .NET, выполнив следующую команду:

        ```dotnetcli
        dotnet --version
        ```

        Убедитесь, что отображаемая версия соответствует установленной версии.

1. Опубликуйте приложение на компьютере разработки, как показано ниже, в зависимости от среды разработки.
    - При использовании **Visual Studio** [разверните приложение в локальной папке](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019). Перед публикацией выберите **изменить** в сводке профиля публикации и перейдите на вкладку **Параметры** . Убедитесь, что для **режима развертывания** задано значение " *зависимая от платформы* ", а **Целевая среда выполнения** — " *Переносимая*".
    - При использовании **интерфейса командной строки .NET** используйте команду [DotNet Publish](../core/tools/dotnet-publish.md) . Дополнительные аргументы не требуются.

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. В командной строке Bash на Raspberry Pi (Local или SSH) запустите приложение. Для этого задайте папку развертывания в качестве текущего каталога и выполните следующую команду (где *HelloWorld.dll* является точкой входа приложения):

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a>Развертывание автономного приложения

Чтобы развернуть приложение как автономное приложение, выполните следующие действия.

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. Опубликуйте приложение на компьютере разработки, как показано ниже, в зависимости от среды разработки.
    - При использовании **Visual Studio** [разверните приложение в локальной папке](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019). Перед публикацией выберите **изменить** в сводке профиля публикации и перейдите на вкладку **Параметры** . Убедитесь, что для **режима развертывания** задано *автономное* и **Целевая среда выполнения** имеет значение *Linux-ARM*.
    - При использовании **интерфейса командной строки .NET** используйте команду [DotNet Publish](../core/tools/dotnet-publish.md) с `-r linux-arm` аргументом:

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. В командной строке Bash на Raspberry Pi (Local или SSH) запустите приложение. Для этого задайте в качестве текущего каталога расположение развертывания и выполните следующие действия.
    1. Предоставьте исполняемому файлу разрешение *EXECUTE* (где `HelloWorld` — имя исполняемого файла).

        ```bash
        chmod +x HelloWorld
        ```

    1. Запустите исполняемый файл.

        ```bash
        ./HelloWorld
        ```
