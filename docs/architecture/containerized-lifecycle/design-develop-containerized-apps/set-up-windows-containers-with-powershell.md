---
title: Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)
description: Сведения об использовании PowerShell при работе с Docker в контейнерах Windows
ms.date: 08/06/2020
ms.openlocfilehash: 6096e4cbad4fb37b485d595c650dc10dc5ed5a22
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434816"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="46214-103">Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)</span><span class="sxs-lookup"><span data-stu-id="46214-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="46214-104">[Контейнеры Windows](/virtualization/windowscontainers/about/index) позволяют преобразовывать существующие приложения Windows в образы Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="46214-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="46214-105">Чтобы использовать контейнеры Windows, нужно попросту добавить команды Windows PowerShell в Dockerfile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="46214-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="46214-106">В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core и служб IIS.</span><span class="sxs-lookup"><span data-stu-id="46214-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="46214-107">Аналогичным образом можно также использовать команды Windows PowerShell для настройки дополнительных компонентов, таких как традиционные технологии ASP.NET 4.x и .NET 4.6, а также другого программного обеспечения Windows следующим образом:</span><span class="sxs-lookup"><span data-stu-id="46214-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="46214-108">[Назад](visual-studio-tools-for-docker.md)
>[Вперед](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="46214-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
