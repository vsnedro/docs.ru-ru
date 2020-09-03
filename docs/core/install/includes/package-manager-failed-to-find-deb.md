---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132952"
---

Если появляется сообщение об ошибке, похожее на **Не удалось найти пакет {netcore-package}** или **Не удалось установить некоторые пакеты**, выполните проведенные ниже команды.

В следующем наборе команд есть два заполнителя.

- `{dotnet-package}`\
Этот заполнитель представляет собой устанавливаемый пакет .NET Core, например `aspnetcore-runtime-3.1`. Он используется в приведенной ниже команде `sudo apt-get install`.

- `{os-version}`\
Этот заполнитель представляет собой используемую версию Linux. Он используется в приведенной ниже команде `wget`.

Сначала попробуйте очистить список пакетов.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Затем попробуйте установить .NET Core еще раз. Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.
