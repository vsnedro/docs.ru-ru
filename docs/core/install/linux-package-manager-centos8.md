---
title: Установка .NET Core в диспетчере пакетов Linux CentOS 8 — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на CentOS 8.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728507"
---
# <a name="centos-8-package-manager---install-net-core"></a>Диспетчер пакетов CentOS 8 — установка .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на CentOS 8.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

В терминале выполните приведенную ниже команду.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

В терминале выполните приведенную ниже команду.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

В терминале выполните приведенную ниже команду.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Установка других версий

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
