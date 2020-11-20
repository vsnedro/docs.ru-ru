---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506983"
---

Если появляется сообщение об ошибке, похожее на **Не удалось найти пакет {dotnet-package}** или **Не удалось установить некоторые пакеты**, выполните проведенные ниже команды.

В следующем наборе команд есть два заполнителя.

- `{dotnet-package}`\
Этот заполнитель представляет собой устанавливаемый пакет .NET, например `aspnetcore-runtime-3.1`. Это используется в следующей команде `sudo apt-get install`.

- `{os-version}`\
Этот заполнитель представляет собой используемую версию Linux. Он используется в приведенной ниже команде `wget`.

Сначала попробуйте очистить список пакетов.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Затем попробуйте установить .NET еще раз. Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.
