---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602750"
---

Если появляется сообщение об ошибке, похожее на **Unable to locate package {netcore-package}** (Не удалось найти пакет {netcore-package}), выполните проведенные ниже команды.

В следующем наборе команд есть два заполнителя.

- `{dotnet-package}`\
Этот заполнитель представляет собой устанавливаемый пакет .NET Core, например `aspnetcore-runtime-3.1`. Он используется в приведенной ниже команде `sudo apt-get install`.

- `{os-version}`\
Этот заполнитель представляет собой используемую версию Linux. Он используется в приведенной ниже команде `wget`.

Попробуйте очистить список пакетов:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.
