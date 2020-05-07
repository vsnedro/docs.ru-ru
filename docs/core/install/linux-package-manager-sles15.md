---
title: Установка .NET Core на SLES 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на SLES 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595665"
---
# <a name="sles-15-package-manager---install-net-core"></a>Диспетчер пакетов SLES 15 — установка .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на SLES 15.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a>Добавление ключа и веб-канала репозитория Майкрософт

Перед установкой .NET нужно сделать следующее:

- добавить ключ подписывания пакета Майкрософт в список доверенных ключей;
- добавить репозиторий в диспетчер пакетов;
- установить необходимые зависимости.

Данную операцию достаточно выполнить один раз для каждого компьютера.

Откройте терминал и выполните приведенную ниже команду.

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

В настоящее время пакет установки репозитория Microsoft SLES 15 устанавливает файл *microsoft-prod.repo* в неправильный каталог, мешая поиску пакетов .NET Core в zypper. Чтобы устранить эту проблему, создайте символьную ссылку в правильном каталоге.

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET. В терминале выполните приведенную ниже команду.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Установка других версий

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Устранение неполадок диспетчера пакетов

В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.

### <a name="failed-to-fetch"></a>Ошибка получения

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
