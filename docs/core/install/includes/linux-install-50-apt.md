---
ms.openlocfilehash: 87c7abf6a20dd8e9769f3b3b3cbe271d32fd62c3
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507003"
---

### <a name="install-the-sdk"></a>Установка пакета SDK

Пакет SDK для .NET позволяет разрабатывать приложения с помощью .NET. При установке пакета SDK для .NET не нужно устанавливать соответствующую среду выполнения. Чтобы установить пакет SDK для .NET, выполните приведенные ниже команды.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0
```

> [!IMPORTANT]
> Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-5.0** (Не удалось найти пакет dotnet-sdk-5.0), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).

### <a name="install-the-runtime"></a>Установка среды выполнения

Среда выполнения ASP.NET Core позволяет запускать приложения, созданные с помощью версии .NET без поддержки среды выполнения. Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET. В терминале выполните приведенные ниже команды.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0
```

> [!IMPORTANT]
> Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-5.0** (Не удалось найти пакет aspnetcore-runtime-5.0), см. раздел [Устранение неполадок с APT](#apt-troubleshooting).

В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-5.0` на `dotnet-runtime-5.0`.

```bash
sudo apt-get install -y dotnet-runtime-5.0
```
