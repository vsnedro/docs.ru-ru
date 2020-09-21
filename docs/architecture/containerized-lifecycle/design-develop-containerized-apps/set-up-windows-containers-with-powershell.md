---
title: Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)
description: Сведения об использовании PowerShell при работе с Docker в контейнерах Windows
ms.date: 08/06/2020
ms.openlocfilehash: be30fd4092f51acd4972c05b3c3ccc936aebd884
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539792"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)

[Контейнеры Windows](/virtualization/windowscontainers/about/index) позволяют преобразовывать существующие приложения Windows в образы Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.

Чтобы использовать контейнеры Windows, нужно попросту добавить команды Windows PowerShell в Dockerfile, как показано в следующем примере:

```dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core и служб IIS.

Аналогичным образом можно также использовать команды Windows PowerShell для настройки дополнительных компонентов, таких как традиционные технологии ASP.NET 4.x и .NET 4.6, а также другого программного обеспечения Windows следующим образом:

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Назад](visual-studio-tools-for-docker.md)
>[Вперед](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
