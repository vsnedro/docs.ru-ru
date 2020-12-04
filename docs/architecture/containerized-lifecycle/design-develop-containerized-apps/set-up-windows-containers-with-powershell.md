---
title: Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)
description: Сведения об использовании PowerShell при работе с Docker в контейнерах Windows
ms.date: 08/06/2020
ms.openlocfilehash: d65538c821a848d83915e715ee3a02990b40e836
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681253"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)

[Контейнеры Windows](/virtualization/windowscontainers/about/index) позволяют преобразовывать существующие приложения Windows в образы Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.

Чтобы использовать контейнеры Windows, нужно попросту добавить команды Windows PowerShell в Dockerfile, как показано в следующем примере:

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core и служб IIS.

Аналогичным образом можно также использовать команды Windows PowerShell для настройки дополнительных компонентов, таких как традиционные технологии ASP.NET 4.x и .NET Framework4.6, а также другого программного обеспечения Windows следующим образом:

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Назад](visual-studio-tools-for-docker.md)
>[Вперед](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
