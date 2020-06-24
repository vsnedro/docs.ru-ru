---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602690"
---

[<span data-ttu-id="a1c0a-101">Платформа .NET Core доступна в Snap Store.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="a1c0a-102">Snap-пакет — это пакет приложения и его зависимостей, которые работают без изменений во многих разных дистрибутивах Linux.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="a1c0a-103">Snap-пакеты можно найти и установить с помощью Snap Store.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="a1c0a-104">Дополнительные сведения о Snap см. в [этой статье](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="a1c0a-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="a1c0a-105">В Snap-пакете доступны только поддерживаемые версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="a1c0a-106">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="a1c0a-106">Install the SDK</span></span>

<span data-ttu-id="a1c0a-107">Snap-пакеты пакета SDK для .NET Core публикуются с одним и тем же идентификатором: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-107">Snap packages for .NET Core SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="a1c0a-108">Конкретную версию пакета SDK можно установить, указав канал.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="a1c0a-109">Пакет SDK содержит соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="a1c0a-110">В следующей таблице перечислены каналы:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-110">The following table list the channels:</span></span>

| <span data-ttu-id="a1c0a-111">Версия .NET Core</span><span class="sxs-lookup"><span data-stu-id="a1c0a-111">.NET Core version</span></span> | <span data-ttu-id="a1c0a-112">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="a1c0a-112">Snap package</span></span>             |
|-------------------|--------------------------|
| <span data-ttu-id="a1c0a-113">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="a1c0a-113">3.1 (LTS)</span></span>         | <span data-ttu-id="a1c0a-114">`3.1` или `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="a1c0a-114">`3.1` or `latest/stable`</span></span> |
| <span data-ttu-id="a1c0a-115">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="a1c0a-115">2.1 (LTS)</span></span>         | `2.1`                    |
| <span data-ttu-id="a1c0a-116">Предварительная версия .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a1c0a-116">.NET 5.0 preview</span></span>  | `5.0/beta`               |

<span data-ttu-id="a1c0a-117">Выполните команду `snap install`, чтобы установить Snap-пакет пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-117">Use the `snap install` command to install a .NET Core SDK snap package.</span></span> <span data-ttu-id="a1c0a-118">Используйте параметр `--channel`, чтобы указать, какую версию следует установить.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-118">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="a1c0a-119">Если этот параметр отсутствует, используйте `latest/stable`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-119">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="a1c0a-120">В этом примере указан `3.1`:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-120">In this example, `3.1` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

<span data-ttu-id="a1c0a-121">Затем зарегистрируйте команду `dotnet` для системы, выполнив команду `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-121">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="a1c0a-122">Эта команда имеет следующий формат: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-122">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="a1c0a-123">Вы можете выбрать любое имя `{alias}`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-123">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="a1c0a-124">Например, вы можете присвоить команде имя после установки конкретной версии с помощью Snap-пакета: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-124">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span></span> <span data-ttu-id="a1c0a-125">При использовании команды `dotnet31` вы вызываете эту конкретную версию .NET.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-125">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="a1c0a-126">Но это несовместимо с инструкциями из большинства учебников и примеров, так как для них необходимо, чтобы команда `dotnet` была доступна.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-126">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="a1c0a-127">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a1c0a-127">Install the runtime</span></span>

<span data-ttu-id="a1c0a-128">Snap-пакеты для среды выполнения .NET Core публикуются с собственными идентификаторами пакета.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-128">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="a1c0a-129">В следующей таблице перечислены идентификаторы пакетов:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-129">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="a1c0a-130">Версия .NET Core</span><span class="sxs-lookup"><span data-stu-id="a1c0a-130">.NET Core version</span></span> | <span data-ttu-id="a1c0a-131">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="a1c0a-131">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="a1c0a-132">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="a1c0a-132">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="a1c0a-133">3.0</span><span class="sxs-lookup"><span data-stu-id="a1c0a-133">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="a1c0a-134">2.2</span><span class="sxs-lookup"><span data-stu-id="a1c0a-134">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="a1c0a-135">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="a1c0a-135">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="a1c0a-136">Выполните команду `snap install`, чтобы установить Snap-пакет среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-136">Use the `snap install` command to install a .NET Core Runtime snap package.</span></span> <span data-ttu-id="a1c0a-137">В этом примере устанавливается .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-137">In this example, .NET Core 3.1 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-31 --classic
```

<span data-ttu-id="a1c0a-138">Затем зарегистрируйте команду `dotnet` для системы, выполнив команду `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-138">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

<span data-ttu-id="a1c0a-139">Эта команда имеет следующий формат: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-139">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="a1c0a-140">Вы можете выбрать любое имя `{alias}`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-140">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="a1c0a-141">Например, вы можете присвоить команде имя после установки конкретной версии с помощью Snap-пакета: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-141">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span></span> <span data-ttu-id="a1c0a-142">При использовании команды `dotnet31` вы вызываете эту конкретную версию .NET.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-142">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="a1c0a-143">Но это несовместимо с инструкциями из большинства учебников и примеров, так как для них необходимо, чтобы команда `dotnet` была доступна.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-143">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="a1c0a-144">Ошибки SSL-сертификатов</span><span class="sxs-lookup"><span data-stu-id="a1c0a-144">SSL Certificate errors</span></span>

<span data-ttu-id="a1c0a-145">При установке .NET с помощью Snap-пакета возможно, что на некоторых дистрибутивах нельзя найти SSL-сертификаты .NET, а во время выполнения `restore` может отобразиться сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-145">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="a1c0a-146">Чтобы устранить эту проблему, задайте несколько переменных среды:</span><span class="sxs-lookup"><span data-stu-id="a1c0a-146">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="a1c0a-147">Расположение сертификата зависит от дистрибутива.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-147">The certificate location will vary by distro.</span></span> <span data-ttu-id="a1c0a-148">Ниже приведены расположения для дистрибутивов, в которых возникла проблема.</span><span class="sxs-lookup"><span data-stu-id="a1c0a-148">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="a1c0a-149">Fedora — `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="a1c0a-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="a1c0a-150">OpenSUSE — `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="a1c0a-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="a1c0a-151">Solus — `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="a1c0a-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
