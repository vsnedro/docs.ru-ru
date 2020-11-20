---
ms.openlocfilehash: ed269683f5c4569c21ae53e9a3c1ec65eb5ebd43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506872"
---

### <a name="install-the-sdk"></a>Установка пакета SDK

Пакет SDK для .NET позволяет разрабатывать приложения с помощью .NET. При установке пакета SDK для .NET не нужно устанавливать соответствующую среду выполнения. Чтобы установить пакет SDK для .NET, выполните приведенные ниже команды.

```bash
sudo zypper install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>Установка среды выполнения

Среда выполнения ASP.NET Core позволяет запускать приложения, созданные с помощью версии .NET без поддержки среды выполнения. Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET. В терминале выполните приведенные ниже команды.

```bash
sudo zypper install aspnetcore-runtime-5.0
```

В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-5.0` на `dotnet-runtime-5.0`.

```bash
sudo zypper install dotnet-runtime-5.0
```
