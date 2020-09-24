---
title: Установка .NET Core в openSUSE (.NET Core)
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: ccdb23ca1838d2c15c9a95b45c8505efe7a6df0e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539234"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a>Установка пакета SDK для .NET Core или среды выполнения .NET Core в openSUSE

.NET Core поддерживается в openSUSE. В этой статье описано, как установить .NET Core в openSUSE.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Поддерживаемые дистрибутивы

В следующей таблице приведен список выпусков .NET Core, которые сейчас поддерживаются в openSUSE 15. Эти версии поддерживаются до тех пор, пока для версии [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или версии openSUSE не будет прекращена поддержка.

- Значок ✔️ означает, что версия openSUSE или .NET Core поддерживается.
- Значок ❌ означает, что версия openSUSE или версия .NET Core в таком выпуске openSUSE не поддерживается.
- Если значок ✔️ стоит как напротив версии openSUSE, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | Предварительная версия .NET 5 (только установка вручную) |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](#opensuse-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (предварительная версия) |

Следующие версии .NET Core больше не поддерживаются (но остаются доступными для скачивания):

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Установка других версий

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a>openSUSE 15 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a>Устранение неполадок диспетчера пакетов

В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.

### <a name="unable-to-find-package"></a>Не удалось найти пакет

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>Ошибка получения

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a>Snap-пакеты

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Зависимости

Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически. Но если вы устанавливаете .NET Core вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:

- krb5
- libicu
- libopenssl1_0_0

Если в целевой среде выполнения установлена версия OpenSSL 1.1 или более поздняя, необходимо установить **compat-openssl10**.

Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:

- [libgdiplus (версии 6.0.1 или выше)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono. Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Установка с помощью скрипта

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Установка вручную

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Следующие шаги

- [Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code](../tutorials/with-visual-studio-code.md)
