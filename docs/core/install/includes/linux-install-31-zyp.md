---
ms.openlocfilehash: 36f1ee26def82d426b6637ae96f382fc89791a2f
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135957"
---

### <a name="install-the-sdk"></a>Установка пакета SDK

Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core. Чтобы установить пакет SDK для .NET Core, выполните приведенные ниже команды.

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a>Установка среды выполнения

Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения. Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core. В терминале выполните приведенные ниже команды.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `aspnetcore-runtime-2.1` на `dotnet-runtime-3.1`.

```bash
sudo zypper install dotnet-runtime-3.1
```
