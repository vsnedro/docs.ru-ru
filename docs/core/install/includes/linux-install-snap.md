---
ms.openlocfilehash: 4ab2fc0645f76870dead99b5f45eef763643fb27
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506905"
---

[Платформа .NET Core доступна в Snap Store.](https://snapcraft.io/dotnet-sdk)

Snap-пакет — это пакет приложения и его зависимостей, которые работают без изменений во многих разных дистрибутивах Linux. Snap-пакеты можно найти и установить с помощью Snap Store. Дополнительные сведения о Snap см. в [этой статье](https://snapcraft.io/docs/getting-started).

В Snap-пакете доступны только поддерживаемые версии .NET Core.

### <a name="install-the-sdk"></a>Установка пакета SDK

Snap-пакеты пакета SDK для .NET публикуются с одним и тем же идентификатором: `dotnet-sdk`. Конкретную версию пакета SDK можно установить, указав канал. Пакет SDK содержит соответствующую среду выполнения. В следующей таблице перечислены каналы:

| Версия .NET | Snap-пакет             |
|--------------|--------------------------|
| 5,0          | `5.0` или `latest/stable` |
| 3.1 (LTS)    | `3.1` или `lts/stable`    |
| 2.1 (LTS)    | `2.1`                    |

Выполните команду `snap install`, чтобы установить Snap-пакет пакета SDK для .NET. Используйте параметр `--channel`, чтобы указать, какую версию следует установить. Если этот параметр отсутствует, используйте `latest/stable`. В этом примере указан `5.0`:

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

Затем зарегистрируйте команду `dotnet` для системы, выполнив команду `snap alias`:

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

Эта команда имеет следующий формат: `sudo snap alias {package}.{command} {alias}`. Вы можете выбрать любое имя `{alias}`. Например, вы можете присвоить команде имя после установки конкретной версии с помощью Snap-пакета: `sudo snap alias dotnet-sdk.dotnet dotnet50`. При использовании команды `dotnet50` вы вызываете эту конкретную версию .NET. Но это несовместимо с инструкциями из большинства учебников и примеров, так как для них необходимо, чтобы команда `dotnet` была доступна.

### <a name="install-the-runtime"></a>Установка среды выполнения

Snap-пакеты для среды выполнения .NET Core публикуются с собственными идентификаторами пакета. В следующей таблице перечислены идентификаторы пакетов:

| Версия .NET      | Snap-пакет        |
|-------------------|---------------------|
| 5,0               | `dotnet-runtime-50` |
| 3.1 (LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2.1 (LTS)         | `dotnet-runtime-21` |

Выполните команду `snap install`, чтобы установить Snap-пакет среды выполнения .NET. В этом примере устанавливается .NET 5.0:

```bash
sudo snap install dotnet-runtime-50 --classic
```

Затем зарегистрируйте команду `dotnet` для системы, выполнив команду `snap alias`:

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

Эта команда имеет следующий формат: `sudo snap alias {package}.{command} {alias}`. Вы можете выбрать любое имя `{alias}`. Например, вы можете присвоить команде имя после установки конкретной версии с помощью Snap-пакета: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`. При использовании команды `dotnet50` вы вызываете эту конкретную версию .NET. Но это несовместимо с инструкциями из большинства учебников и примеров, так как для них необходимо, чтобы команда `dotnet` была доступна.

### <a name="ssl-certificate-errors"></a>Ошибки SSL-сертификатов

При установке .NET с помощью Snap-пакета возможно, что на некоторых дистрибутивах нельзя найти SSL-сертификаты .NET, а во время выполнения `restore` может отобразиться сообщение об ошибке:

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

Чтобы устранить эту проблему, задайте несколько переменных среды:

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

Расположение сертификата зависит от дистрибутива. Ниже приведены расположения для дистрибутивов, в которых возникла проблема.

* Fedora — `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
* OpenSUSE — `/etc/ssl/ca-bundle.pem`
* Solus — `/etc/ssl/certs/ca-certificates.crt`
