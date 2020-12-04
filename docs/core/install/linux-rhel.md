---
title: Установка .NET в RHEL — .NET
description: Здесь приводятся различные способы установки пакета SDK для .NET и среды выполнения .NET в RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 931cad51ff8e35ff16b67ff9b795feb36010a66b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031791"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a>Установка пакета SDK для .NET или среды выполнения .NET в RHEL

.NET поддерживается в RHEL. В этой статье описано, как установить .NET в RHEL.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Регистрация подписки Red Hat

Чтобы установить .NET из Red Hat в RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat. Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET](https://access.redhat.com/documentation/net/5.0/).

## <a name="supported-distributions"></a>Поддерживаемые дистрибутивы

В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET в RHEL 7 и RHEL 8. Эти версии поддерживаются до того же времени, что и версия [.NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или RHEL.

- Значок ✔️ означает, что версия RHEL или .NET поддерживается.
- Значок ❌ означает, что версия RHEL или версия .NET в таком выпуске RHEL не поддерживается.
- Если значок ✔️ стоит как напротив версии RHEL, так и напротив версии .NET, это значит, что такое сочетание ОС и .NET поддерживается.

| RHEL                     | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-)        | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](#rhel-7--net-50) | ✔️ 2.1        | ✔️ [3.1](#rhel-7--net-core-31)        | ✔️ [5.0](#rhel-7--net-50) |

Следующие версии .NET больше не поддерживаются. (но остаются доступными для скачивания):

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>Удалите предварительные версии

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a>Установка других версий

Сведения об установке других выпусков .NET см. в [документации по Red Hat для .NET](https://access.redhat.com/documentation/net/5.0/).

## <a name="rhel-8-"></a>RHEL 8 ✔️

> [!TIP]
> .NET 5.0 пока недоступна в репозиториях AppStream, однако .NET Core 3.1 доступна. Чтобы установить .NET Core 3.1, используйте команду `dnf install` с соответствующим пакетом, например `aspnetcore-runtime-3.1` или `dotnet-sdk-3.1`. Следующие действия приведены для .NET 5.0.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a>RHEL 7 ✔️ .NET 5.0

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a>RHEL 7 ✔️ .NET Core 3.1

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

Следующая команда устанавливает пакет `scl-utils`:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Установка пакета SDK

Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core. При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения. Чтобы установить пакет SDK для .NET Core, выполните следующие команды:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

В Red Hat не рекомендуется активировать `rh-dotnet31` на постоянной основе, так как это может повлиять на другие программы. Например, `rh-dotnet31` включает версию `libcurl`, которая отличается от базовой версии RHEL. Это может вызвать проблемы в программах, которые не ожидают другой версии `libcurl`. Если вы хотите активировать `rh-dotnet` на постоянной основе, добавьте следующую строку в файл _~/.bashrc_.

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a>Установка среды выполнения

Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения. Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core. В терминале выполните приведенные ниже команды.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

В Red Hat не рекомендуется активировать `rh-dotnet31-aspnetcore-runtime-3.1` на постоянной основе, так как это может повлиять на другие программы. Например, `rh-dotnet31-aspnetcore-runtime-3.1` включает версию `libcurl`, которая отличается от базовой версии RHEL. Это может вызвать проблемы в программах, которые не ожидают другой версии `libcurl`. Если вы хотите активировать `rh-dotnet31-aspnetcore-runtime-3.1` на постоянной основе, добавьте следующую строку в файл _~/.bashrc_.

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `rh-dotnet31-aspnetcore-runtime-3.1` на `rh-dotnet31-dotnet-runtime-3.1`.

## <a name="snap"></a>Snap-пакеты

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Зависимости

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a>Установка с помощью скрипта

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Установка вручную

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Следующие шаги

- [Учебник. Создание консольного приложения с помощью пакета SDK для .NET в Visual Studio Code](../tutorials/with-visual-studio-code.md)
