---
title: DOCKER-gRPC для разработчиков WCF
description: Создание образов DOCKER для ASP.NET Core приложений gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 379750edfa1a9fc282e43ffa83e5695425f31a26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152719"
---
# <a name="create-docker-images"></a><span data-ttu-id="ba665-103">Создание образов DOCKER</span><span class="sxs-lookup"><span data-stu-id="ba665-103">Create Docker images</span></span>

<span data-ttu-id="ba665-104">В этом разделе рассматриваются создание образов DOCKER для приложений ASP.NET Core gRPC, готовых к работе в DOCKER, Kubernetes или в других средах контейнеров.</span><span class="sxs-lookup"><span data-stu-id="ba665-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="ba665-105">Пример приложения, используемый с веб-приложением ASP.NET Core MVC и службой gRPC, доступен в репозитории [DotNet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="ba665-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="ba665-106">Базовые образы Майкрософт для приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ba665-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="ba665-107">Корпорация Майкрософт предоставляет ряд базовых образов для создания и запуска приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ba665-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="ba665-108">Чтобы создать образ ASP.NET Core 3,0, используйте два базовых образа:</span><span class="sxs-lookup"><span data-stu-id="ba665-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="ba665-109">Образ пакета SDK для сборки и публикации приложения.</span><span class="sxs-lookup"><span data-stu-id="ba665-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="ba665-110">Образ среды выполнения для развертывания.</span><span class="sxs-lookup"><span data-stu-id="ba665-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="ba665-111">Изображение</span><span class="sxs-lookup"><span data-stu-id="ba665-111">Image</span></span> | <span data-ttu-id="ba665-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ba665-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="ba665-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="ba665-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="ba665-114">Для создания приложений с помощью `docker build` .</span><span class="sxs-lookup"><span data-stu-id="ba665-114">For building applications with `docker build`.</span></span> <span data-ttu-id="ba665-115">Не для использования в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="ba665-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="ba665-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="ba665-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="ba665-117">Содержит зависимости среды выполнения и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ba665-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="ba665-118">Для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="ba665-118">For production.</span></span> |

<span data-ttu-id="ba665-119">Для каждого образа существует четыре варианта, основанные на разных дистрибутивах Linux, различающихся по тегам.</span><span class="sxs-lookup"><span data-stu-id="ba665-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="ba665-120">Теги изображений</span><span class="sxs-lookup"><span data-stu-id="ba665-120">Image tag(s)</span></span> | <span data-ttu-id="ba665-121">Linux</span><span class="sxs-lookup"><span data-stu-id="ba665-121">Linux</span></span> | <span data-ttu-id="ba665-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba665-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="ba665-123">3,0-бустер, 3,0</span><span class="sxs-lookup"><span data-stu-id="ba665-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="ba665-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="ba665-124">Debian 10</span></span> | <span data-ttu-id="ba665-125">Изображение по умолчанию, если не указан вариант ОС.</span><span class="sxs-lookup"><span data-stu-id="ba665-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="ba665-126">3,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="ba665-126">3.0-alpine</span></span> | <span data-ttu-id="ba665-127">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="ba665-127">Alpine 3.9</span></span> | <span data-ttu-id="ba665-128">Базовые образы Alpine намного меньше, чем Debian или Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="ba665-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="ba665-129">3,0-Disco</span><span class="sxs-lookup"><span data-stu-id="ba665-129">3.0-disco</span></span> | <span data-ttu-id="ba665-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="ba665-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="ba665-131">3,0-Бионик</span><span class="sxs-lookup"><span data-stu-id="ba665-131">3.0-bionic</span></span> | <span data-ttu-id="ba665-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="ba665-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="ba665-133">Базовый образ Alpine составляет около 100 МБ по сравнению с 200 МБ для образов Debian и Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="ba665-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="ba665-134">Некоторые программные пакеты или библиотеки могут быть недоступны в управлении пакетами Alpine.</span><span class="sxs-lookup"><span data-stu-id="ba665-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="ba665-135">Если вы не знаете, какой образ следует использовать, то, вероятно, вам нужно выбрать Debian по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba665-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba665-136">Убедитесь, что для сборки и среды выполнения используется один и тот же вариант Linux.</span><span class="sxs-lookup"><span data-stu-id="ba665-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="ba665-137">Приложения, созданные и опубликованные на одном варианте, могут не работать на другом.</span><span class="sxs-lookup"><span data-stu-id="ba665-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="ba665-138">Создайте образ Docker.</span><span class="sxs-lookup"><span data-stu-id="ba665-138">Create a Docker image</span></span>

<span data-ttu-id="ba665-139">Образ DOCKER определяется *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="ba665-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="ba665-140">Это текстовый файл, содержащий все команды, необходимые для создания приложения, и установки всех зависимостей, необходимых для сборки или запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="ba665-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="ba665-141">В следующем примере показан самый простой Dockerfile для приложения ASP.NET Core 3,0:</span><span class="sxs-lookup"><span data-stu-id="ba665-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="ba665-142">Dockerfile состоит из двух частей: первый использует `sdk` базовый образ для сборки и публикации приложения, второй создает образ среды выполнения из `aspnet` базы.</span><span class="sxs-lookup"><span data-stu-id="ba665-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="ba665-143">Это связано с тем `sdk` , что изображение составляет около 900 МБ по сравнению с 200 МБ для образа среды выполнения, и большая часть его содержимого не требуется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ba665-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="ba665-144">Этапы сборки</span><span class="sxs-lookup"><span data-stu-id="ba665-144">The build steps</span></span>

| <span data-ttu-id="ba665-145">Шаг</span><span class="sxs-lookup"><span data-stu-id="ba665-145">Step</span></span> | <span data-ttu-id="ba665-146">Описание</span><span class="sxs-lookup"><span data-stu-id="ba665-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="ba665-147">Объявляет базовый образ и присваивает ему `builder` псевдоним.</span><span class="sxs-lookup"><span data-stu-id="ba665-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="ba665-148">Создает `/src` каталог и задает его в качестве текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="ba665-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="ba665-149">Копирует все, что находится под текущим каталогом на узле, в текущий каталог на образе.</span><span class="sxs-lookup"><span data-stu-id="ba665-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="ba665-150">Восстанавливает все внешние пакеты (ASP.NET Core 3,0 Framework предварительно устанавливается вместе с пакетом SDK).</span><span class="sxs-lookup"><span data-stu-id="ba665-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="ba665-151">Создает и публикует сборку выпуска.</span><span class="sxs-lookup"><span data-stu-id="ba665-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="ba665-152">Обратите внимание, что `--runtime` флаг не требуется.</span><span class="sxs-lookup"><span data-stu-id="ba665-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="ba665-153">Шаги образа среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ba665-153">The runtime image steps</span></span>

| <span data-ttu-id="ba665-154">Шаг</span><span class="sxs-lookup"><span data-stu-id="ba665-154">Step</span></span> | <span data-ttu-id="ba665-155">Описание</span><span class="sxs-lookup"><span data-stu-id="ba665-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="ba665-156">Объявляет новый базовый образ.</span><span class="sxs-lookup"><span data-stu-id="ba665-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="ba665-157">Создает `/app` каталог и задает его в качестве текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="ba665-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="ba665-158">Копирует опубликованное приложение из предыдущего образа, используя `builder` псевдоним из первой `FROM` строки.</span><span class="sxs-lookup"><span data-stu-id="ba665-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="ba665-159">Задает выполнение команды при запуске контейнера.</span><span class="sxs-lookup"><span data-stu-id="ba665-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="ba665-160">`dotnet`Команда в образе среды выполнения может запускать только DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="ba665-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="ba665-161">HTTPS в DOCKER</span><span class="sxs-lookup"><span data-stu-id="ba665-161">HTTPS in Docker</span></span>

<span data-ttu-id="ba665-162">Базовые образы Майкрософт для DOCKER задают `ASPNETCORE_URLS` для переменной среды значение `http://+:80` , означающее, что Kestrel выполняется без протокола HTTPS для этого порта.</span><span class="sxs-lookup"><span data-stu-id="ba665-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="ba665-163">Если вы используете протокол HTTPS с пользовательским сертификатом (как описано в разделе Локальные [приложения gRPC](self-hosted.md)), его следует переопределить.</span><span class="sxs-lookup"><span data-stu-id="ba665-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="ba665-164">Задайте переменную среды в части Dockerfile, созданной в образе среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ba665-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="ba665-165">Файл dockerignore</span><span class="sxs-lookup"><span data-stu-id="ba665-165">The .dockerignore file</span></span>

<span data-ttu-id="ba665-166">Во многом подобно `.gitignore` файлам, которые исключают определенные файлы и каталоги из системы управления версиями, `.dockerignore` файл можно использовать для исключения копирования файлов и каталогов в образ во время сборки.</span><span class="sxs-lookup"><span data-stu-id="ba665-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="ba665-167">Это не только экономит время, но и позволяет избежать некоторых ошибок, возникающих при `obj` копировании каталога с компьютера в образ.</span><span class="sxs-lookup"><span data-stu-id="ba665-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="ba665-168">Как минимум, необходимо добавить в файл записи для `bin` и `obj` `.dockerignore` .</span><span class="sxs-lookup"><span data-stu-id="ba665-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="ba665-169">Создание образа</span><span class="sxs-lookup"><span data-stu-id="ba665-169">Build the image</span></span>

<span data-ttu-id="ba665-170">Для решения с одним приложением и, таким способом, одним Dockerfile, проще всего разместить Dockerfile в базовом каталоге.</span><span class="sxs-lookup"><span data-stu-id="ba665-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="ba665-171">Иными словами, помещайте его в тот же каталог, что и `.sln` файл.</span><span class="sxs-lookup"><span data-stu-id="ba665-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="ba665-172">В этом случае для сборки образа используйте следующую `docker build` команду из каталога, содержащего Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="ba665-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="ba665-173">Флаг с непонятным именем `--tag` (который можно сократить до `-t` ) задает полное имя изображения, включая фактический тег, если он указан.</span><span class="sxs-lookup"><span data-stu-id="ba665-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="ba665-174">В `.` конце указывается контекст, в котором будет выполняться сборка; текущий рабочий каталог для `COPY` команд в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="ba665-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="ba665-175">Если в одном решении имеется несколько приложений, Dockerfile можно разместить для каждого приложения в отдельной папке рядом с `.csproj` файлом.</span><span class="sxs-lookup"><span data-stu-id="ba665-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="ba665-176">Необходимо по-прежнему выполнить `docker build` команду из базового каталога, чтобы убедиться, что решение и все проекты скопированы в образ.</span><span class="sxs-lookup"><span data-stu-id="ba665-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="ba665-177">Можно указать Dockerfile под текущим каталогом с помощью `--file` `-f` флага (или).</span><span class="sxs-lookup"><span data-stu-id="ba665-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="ba665-178">Запуск образа в контейнере на компьютере</span><span class="sxs-lookup"><span data-stu-id="ba665-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="ba665-179">Чтобы запустить образ в локальном экземпляре DOCKER, используйте `docker run` команду.</span><span class="sxs-lookup"><span data-stu-id="ba665-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="ba665-180">`-ti`Флаг подключает текущий терминал к терминалу контейнера и выполняется в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="ba665-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="ba665-181">`-p 5000:80`Порт 80 в контейнере публикуется (Links) для порта 5000 на сетевом интерфейсе localhost.</span><span class="sxs-lookup"><span data-stu-id="ba665-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="ba665-182">Отправка образа в реестр</span><span class="sxs-lookup"><span data-stu-id="ba665-182">Push the image to a registry</span></span>

<span data-ttu-id="ba665-183">Убедившись, что образ работает, отправьте его в реестр DOCKER, чтобы сделать доступным в других системах.</span><span class="sxs-lookup"><span data-stu-id="ba665-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="ba665-184">Внутренним сетям потребуется подготавливать реестр DOCKER.</span><span class="sxs-lookup"><span data-stu-id="ba665-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="ba665-185">Это может быть так же просто, как и [собственный `registry` образ DOCKER](https://docs.docker.com/registry/deploying/) (реестр DOCKER выполняется в контейнере DOCKER), но доступны различные более комплексные решения.</span><span class="sxs-lookup"><span data-stu-id="ba665-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="ba665-186">Для внешнего общего доступа и использования в облаке доступны различные управляемые реестры, такие как [Реестр контейнеров Azure](/azure/container-registry/) или [DOCKER Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="ba665-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="ba665-187">Чтобы отправить в центр DOCKER, перед именем образа необходимо указать имя пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="ba665-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="ba665-188">Чтобы отправить в частный реестр, добавьте перед именем образа имя узла реестра и имя Организации.</span><span class="sxs-lookup"><span data-stu-id="ba665-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="ba665-189">После того как образ находится в реестре, его можно развернуть на отдельных узлах DOCKER или в подсистеме оркестрации контейнеров, например Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="ba665-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ba665-190">[Назад](self-hosted.md)
>[Вперед](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="ba665-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
