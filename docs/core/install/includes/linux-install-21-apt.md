---
ms.openlocfilehash: f7cd60f02a51516b8e35cdb9014fa8b96a188ae2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506978"
---

### <a name="install-the-sdk"></a>Установка пакета SDK

Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core. При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения. Чтобы установить пакет SDK для .NET Core, выполните приведенные ниже команды.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-2.1** (Не удалось найти пакет dotnet-sdk-2.1), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).

### <a name="install-the-runtime"></a>Установка среды выполнения

Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения. Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core. В терминале выполните приведенные ниже команды.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-2.1** (Не удалось найти пакет aspnetcore-runtime-2.1), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).

В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-2.1` на `dotnet-runtime-2.1`.

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
