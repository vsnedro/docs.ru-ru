---
title: Отладка приложений .NET на Raspberry Pi
description: Узнайте, как выполнять отладку приложений .NET на Raspberry Pi и аналогичных устройствах.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 7b9872304ee53071452772e3da02081a7def4d80
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594017"
---
# <a name="debug-net-apps-on-raspberry-pi"></a>Отладка приложений .NET на Raspberry Pi

Отладка приложений .NET, работающих на устройствах IoT под управлением ARM, таких как Raspberry Pi, представляет собой уникальную задачу. Приложения .NET можно разрабатывать на устройствах ARM. Однако OmniSharp, необходимый для отладки приложений .NET вне Visual Studio, несовместим с устройствами ARM. В результате приложения должны быть отлажены удаленно с совместимой платформы.

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a>Отладка из Visual Studio Code (кросс-платформенные)

Для отладки .NET на платформе Raspberry Pi с Visual Studio Code требуется выполнить действия по настройке Raspberry Pi и файла проекта в *launch.js* .

### <a name="enable-ssh-on-the-raspberry-pi"></a>Включение SSH в Raspberry Pi

Для удаленной отладки требуется SSH. Сведения о включении SSH см. в [разделе *Включение SSH* в документации по Raspberry Pi](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span> .

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a>Установка Удаленный отладчик Visual Studio на устройстве Raspberry Pi

В консоли Bash в Raspberry Pi (локально или через SSH) выполните следующие действия.

1. Чтобы скачать и установить Удаленный отладчик Visual Studio на устройстве PI Raspberry, выполните следующую команду:

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. Отладчику требуется запуск от имени `root` . По умолчанию `root` не имеет пароля в Raspberry Pi. Задайте пароль для `root` , выполнив следующую команду и следуя инструкциям на экране.

    ```bash
    sudo passwd root
    ```

1. Visual Studio Code использует протокол SSH для удаленной отладки. В целях безопасности `root` не разрешается входить по протоколу SSH по умолчанию. Чтобы включить `root` Вход через SSH, выполните следующие действия.

    1. Выполните следующую команду, чтобы открыть *каталог/etc/ssh/sshd_config* в [Nano](https://www.nano-editor.org/docs.php) <span class="docon docon-navigate-external x-hidden-focus"></span> .

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. Нажмите клавиши <kbd>CTRL + W</kbd> и выполните поиск по запросу **пермитрутлогин**.
    1. При необходимости раскомментируйте строку с помощью **пермитрутлогин** .
    1. Измените строку для чтения следующим образом:

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > Если в *sshd_config каталог/etc/SSH/* нет строки **пермитрутлогин** , добавьте новую строку со значением, показанным выше.

    1. Нажмите клавиши <kbd>CTRL + X</kbd> , чтобы выйти и сохранить шанс. При появлении запроса **сохранить измененный буфер?** нажмите клавишу <kbd>Y</kbd> для подтверждения. Нажмите клавишу <kbd>Ввод</kbd> , чтобы подтвердить перезапись исходного файла.
    1. Перезагрузите Raspberry Pi, выполнив следующую команду:

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a>launch.jsустановки в Visual Studio Code

Добавьте конфигурацию запуска в *launch.js* проекта. Если в проекте нет *launch.js* файла, добавьте его, перейдя на вкладку **выполнить** , выбрав **создать launch.jsв файле** и выбрав **.NET** или **.NET Core** в диалоговом окне.

Новая конфигурация в *launch.jsв* должна выглядеть следующим образом:

```json
"configurations": [
    {
        "name": ".NET Core Launch (remote console)",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "/home/pi/.dotnet/dotnet",
        "args": ["/home/pi/sample/Sample.dll"],
        "cwd": "/home/pi/sample",
        "stopAtEntry": false,
        "console": "internalConsole",
        "pipeTransport": {
            "pipeCwd": "${workspaceFolder}",
            "pipeProgram": "C:\\Program Files\\PuTTY\\PLINK.EXE",
            "pipeArgs": [
                "-pw",
                "P@ssw0rd",
                "root@raspberrypi"
            ],
            "debuggerPath": "/home/pi/vsdbg/vsdbg"
        }
    },
```

Обратите внимание на следующее.

- `program` — Это путь к среде выполнения .NET на устройстве PI.
- `args` путь к сборке для отладки на устройстве PI.
- `cwd` Рабочий каталог, используемый при запуске приложения на устройстве PI.
- `pipeProgram` — Это путь к SSH-клиенту на локальном компьютере.
- `pipeArgs` параметры, передаваемые клиенту SSH. Обязательно укажите параметр Password, а также `root` пользователя в формате `<user>@<hostname>` .

> [!IMPORTANT]
> В приведенном выше примере используется *Плинк*, компонент клиента [PuTTY](https://www.ssh.com/ssh/putty/) вышеуказанного <span class="docon docon-navigate-external x-hidden-focus"></span> SSH. [OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> Вместо этого можно использовать OpenSSH, который входит в последние версии Windows и Linux. Однако OpenSSH не поддерживает отправку паролей в качестве параметра командной строки. Чтобы использовать OpenSSH, [Настройте Raspberry Pi для доступа SSH, не имеющего пароля](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span> .

### <a name="deploy-the-app"></a>Развертывание приложения

Разверните приложение, как описано в разделе [развертывание приложений .NET для Raspberry Pi](deployment.md). Убедитесь, что путь развертывания совпадает с путем, указанным в `cwd` параметре в *launch.js* конфигурации.

### <a name="launch-the-debugger"></a>Запуск отладчика

На вкладке **выполнить** выберите конфигурацию **запуска .NET Core (удаленная консоль)** и щелкните **начать отладку**. Приложение запускается на устройстве Raspberry Pi. Отладчик можно использовать для установки точек останова, проверки локальных переменных и многого другого.

## <a name="references"></a>Ссылки

[Удаленная отладка с VS Code в Windows до Raspberry Pi с помощью .NET Core на ARM](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)<span class="docon docon-navigate-external x-hidden-focus"></span>

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a>Отладка из Visual Studio в Windows

Visual Studio может выполнять отладку приложений .NET на удаленных устройствах через SSH. На устройстве не требуется специальной настройки. Дополнительные сведения об использовании Visual Studio для удаленной отладки .NET см. в статье [Удаленная отладка .NET в Linux с помощью SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).

::: zone-end
