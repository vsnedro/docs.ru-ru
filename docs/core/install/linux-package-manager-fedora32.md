---
title: Установка .NET Core на Fedora 32 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Fedora 32.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624954"
---
# <a name="fedora-32-package-manager---install-net-core"></a>Диспетчер пакетов Fedora 32 — установка .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

В этой статье описывается, как использовать диспетчер пакетов для установки .NET Core на Fedora 32.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

Начиная с Fedora 32 .NET Core 3.1 доступен в репозиториях пакетов по умолчанию в Fedora.

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

Установите пакет SDK для .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

Установите среду выполнения ASP.NET. В терминале выполните приведенную ниже команду.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

Установите среду выполнения .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Установка других версий

Чтобы установить другие версии .NET Core, вручную установите [пакет SDK для .NET Core](sdk.md?pivots=os-linux#download-and-manually-install) или [среду выполнения .NET Core](runtime.md?pivots=os-linux#download-and-manually-install).
