---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768405"
---

[Сценарии dotnet-install](../../tools/dotnet-install-script.md) используются для автоматизации установок **пакета SDK** и **среды выполнения** и осуществления таких установок без прав администратора. Скрипт можно скачать на странице <https://dot.net/v1/dotnet-install.sh>.

Этот сценарий по умолчанию устанавливает последнюю версию SDK [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Чтобы установить текущий выпуск, который может не быть версией LTS, используйте параметр `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Чтобы вместо пакета SDK установить среду выполнения .NET Core, используйте параметр `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Вы можете установить определенную версию, указав ее в параметре `-c`. Следующая команда устанавливает пакет SDK для .NET Core 3.1.

```bash
./dotnet-install.sh -c 3.1
```

Дополнительные сведения см. в статье [Справка по скриптам dotnet-install](../../tools/dotnet-install-script.md).
