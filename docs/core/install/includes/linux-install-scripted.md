---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602720"
---

Скрипты [dotnet-install](../../tools/dotnet-install-script.md) используются для автоматизации установок пакета **SDK** и их выполнения без прав администратора. Скрипт можно скачать на странице <https://dot.net/v1/dotnet-install.sh>.

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Чтобы установить текущий выпуск, который может не быть версией LTS, используйте параметр `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Чтобы вместо пакета SDK установить среду выполнения .NET Core, используйте параметр `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime
```

Вы можете установить определенную версию, указав ее в параметре `-c`. Следующая команда устанавливает пакет SDK для .NET Core 3.1.

```bash
./dotnet-install.sh -c 3.1
```

Дополнительные сведения см. в статье [Справка по скриптам dotnet-install](../../tools/dotnet-install-script.md).
