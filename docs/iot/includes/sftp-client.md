---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594020"
---
[С помощью клиента SFTP](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md)скопируйте файлы из расположения публикации на компьютере разработчика в новую папку на устройстве Raspberry Pi.

Например, чтобы `scp` скопировать файлы с компьютера разработчика на устройство Raspberry Pi с помощью команды, откройте командную строку и выполните следующую команду:

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

Где:

- `-r`Параметр предписывает `scp` рекурсивно копировать файлы.
- */публиш-локатион/* — это папка, опубликованная на предыдущем шаге.
- `pi@raspberypi` имя пользователя и узла в формате `<username>@<hostname>` .
- */Хоме/Пи/деплоймент-локатион/* — это новая папка на Raspberry Pi.

> [!TIP]
> В последних версиях Windows имеется OpenSSH, включая `scp` предварительно установленные.
