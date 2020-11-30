---
ms.openlocfilehash: 540eebd957ce8ce0928db2bd8317cb220cba30bb
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031775"
---

[Сценарии dotnet-install](../../tools/dotnet-install-script.md) используются для автоматизации установок **пакета SDK** и **среды выполнения** и осуществления таких установок без прав администратора. Скрипт можно скачать на странице <https://dot.net/v1/dotnet-install.sh>.

Этот сценарий по умолчанию устанавливает последнюю версию SDK [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Чтобы установить текущий выпуск, который может не быть версией LTS, используйте параметр `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Чтобы вместо пакета SDK установить среду выполнения .NET, используйте параметр `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Вы можете установить определенную версию, указав ее в параметре `-c`. Следующая команда устанавливает пакет SDK для .NET 5.0.

```bash
./dotnet-install.sh -c 5.0
```

Дополнительные сведения см. в статье [Справка по скриптам dotnet-install](../../tools/dotnet-install-script.md).
