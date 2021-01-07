---
title: DOCKER-gRPC для разработчиков WCF
description: Создание образов DOCKER для ASP.NET Core приложений gRPC
ms.date: 01/06/2021
ms.openlocfilehash: f59518a28b0a1dee75c792ba03bd4af826638502
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970093"
---
# <a name="create-docker-images"></a>Создание образов DOCKER

В этом разделе рассматриваются создание образов DOCKER для приложений ASP.NET Core gRPC, готовых к работе в DOCKER, Kubernetes или в других средах контейнеров. Пример приложения, используемый с веб-приложением ASP.NET Core MVC и службой gRPC, доступен в репозитории [DotNet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Базовые образы Майкрософт для приложений ASP.NET Core

Корпорация Майкрософт предоставляет ряд базовых образов для создания и запуска приложений .NET. Чтобы создать образ ASP.NET Core 5,0, используйте два базовых образа:

- Образ пакета SDK для сборки и публикации приложения.
- Образ среды выполнения для развертывания.

| Изображение | Описание |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/) | Для создания приложений с помощью `docker build` . Не для использования в рабочей среде. |
| [mcr.microsoft.com/dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | Содержит зависимости среды выполнения и ASP.NET Core. Для рабочей среды. |

Для каждого образа существует четыре варианта, основанные на разных дистрибутивах Linux, различающихся по тегам.

| Теги изображений | Linux | Примечания |
| --------- | ----- | ----- |
| 5,0-бустер-тонкий, 5,0 | Debian 10 | Изображение по умолчанию, если не указан вариант ОС. |
| 5,0-Alpine | Alpine 3,12 | Базовые образы Alpine намного меньше, чем Debian или Ubuntu. |
| 5,0 — фокус| Ubuntu 20.04 | |

Базовый образ Alpine составляет около 100 МБ по сравнению с 200 МБ для образов Debian и Ubuntu. Некоторые программные пакеты или библиотеки могут быть недоступны в управлении пакетами Alpine. Если вы не знаете, какой образ следует использовать, то, вероятно, вам нужно выбрать Debian по умолчанию.

> [!IMPORTANT]
> Убедитесь, что для сборки и среды выполнения используется один и тот же вариант Linux. Приложения, созданные и опубликованные на одном варианте, могут не работать на другом.

## <a name="create-a-docker-image"></a>Создайте образ Docker.

Образ DOCKER определяется *Dockerfile*. Этот *Dockerfile* представляет собой текстовый файл, содержащий все команды, необходимые для создания приложения, и установки всех зависимостей, необходимых для сборки или запуска приложения. В следующем примере показан самый простой Dockerfile для приложения ASP.NET Core 5,0:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile состоит из двух частей: первый использует `sdk` базовый образ для сборки и публикации приложения, второй создает образ среды выполнения из `aspnet` базы. Это связано с тем `sdk` , что изображение составляет около 900 МБ по сравнению с 200 МБ для образа среды выполнения, и большая часть его содержимого не требуется во время выполнения.

### <a name="the-build-steps"></a>Этапы сборки

| Шаг | Описание |
| ---- | ----------- |
| `FROM ...` | Объявляет базовый образ и присваивает ему `builder` псевдоним. |
| `WORKDIR /src` | Создает `/src` каталог и задает его в качестве текущего рабочего каталога. |
| `COPY . .` | Копирует все, что находится под текущим каталогом на узле, в текущий каталог на образе. |
| `RUN dotnet restore` | Восстанавливает все внешние пакеты (ASP.NET Core 3,0 Framework предварительно устанавливается вместе с пакетом SDK). |
| `RUN dotnet publish ...` | Создает и публикует сборку выпуска. Обратите внимание, что `--runtime` флаг не требуется. |

### <a name="the-runtime-image-steps"></a>Шаги образа среды выполнения

| Шаг | Описание |
| ---- | ----------- |
| `FROM ...` | Объявляет новый базовый образ. |
| `WORKDIR /app` | Создает `/app` каталог и задает его в качестве текущего рабочего каталога. |
| `COPY --from=builder ...` | Копирует опубликованное приложение из предыдущего образа, используя `builder` псевдоним из первой `FROM` строки. |
| `ENTRYPOINT [ ... ]` | Задает выполнение команды при запуске контейнера. `dotnet`Команда в образе среды выполнения может запускать только DLL-файлы. |

### <a name="https-in-docker"></a>HTTPS в DOCKER

Базовые образы Майкрософт для DOCKER задают `ASPNETCORE_URLS` для переменной среды значение `http://+:80` , означающее, что Kestrel выполняется без протокола HTTPS для этого порта. Если вы используете протокол HTTPS с пользовательским сертификатом (как описано в разделе Локальные [приложения gRPC](self-hosted.md)), следует переопределить эту конфигурацию. Задайте переменную среды в части Dockerfile, созданной в образе среды выполнения.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Файл dockerignore

Во многом подобно `.gitignore` файлам, которые исключают определенные файлы и каталоги из системы управления версиями, `.dockerignore` файл можно использовать для исключения копирования файлов и каталогов в образ во время сборки. Этот файл не только экономит время, но также может избежать некоторых ошибок, возникающих при `obj` копировании каталога с компьютера в образ. Как минимум, необходимо добавить в файл записи для `bin` и `obj` `.dockerignore` .

```console
bin/
obj/
```

## <a name="build-the-image"></a>Создание образа

Для `StockKube.sln` решения, содержащего два разных приложения `StockData` и `StockWeb` , проще всего разместить Dockerfile для каждого из них в базовом каталоге. В этом случае для создания образа используйте следующую `docker build` команду из того же каталога, в котором `.sln` находится файл.

```console
docker build -t stockdata:1.0.0 -f ./src/StockData/Dockerfile .
```

Флаг с непонятным именем `--tag` (который можно сократить до `-t` ) задает полное имя изображения, включая фактический тег, если он указан. В `.` конце указывается контекст, в котором будет выполняться сборка; текущий рабочий каталог для `COPY` команд в Dockerfile.

Если в одном решении имеется несколько приложений, Dockerfile можно разместить для каждого приложения в отдельной папке рядом с `.csproj` файлом. Необходимо по-прежнему выполнить `docker build` команду из базового каталога, чтобы убедиться, что решение и все проекты скопированы в образ. Можно указать Dockerfile под текущим каталогом с помощью `--file` `-f` флага (или).

```console
docker build -t stockdata:1.0.0 -f ./src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Запуск образа в контейнере на компьютере

Чтобы запустить образ в локальном экземпляре DOCKER, используйте `docker run` команду.

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

`-ti`Флаг подключает текущий терминал к терминалу контейнера и выполняется в интерактивном режиме. `-p 5000:80`Порт 80 в контейнере публикуется (Links) для порта 5000 на сетевом интерфейсе localhost.

## <a name="push-the-image-to-a-registry"></a>Отправка образа в реестр

Убедившись, что образ работает, отправьте его в реестр DOCKER, чтобы сделать доступным в других системах. Внутренним сетям потребуется подготавливать реестр DOCKER. Это действие может выполняться так же просто, как и [собственный `registry` образ DOCKER](https://docs.docker.com/registry/deploying/) (реестр DOCKER выполняется в контейнере DOCKER), но доступны различные более комплексные решения. Для внешнего общего доступа и использования в облаке доступны различные управляемые реестры, такие как [Реестр контейнеров Azure](/azure/container-registry/) или [DOCKER Hub](https://docs.docker.com/docker-hub/repos/).

Чтобы отправить в центр DOCKER, перед именем образа необходимо указать имя пользователя или организации.

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

Чтобы отправить в частный реестр, добавьте перед именем образа имя узла реестра и имя Организации.

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

После того как образ находится в реестре, его можно развернуть на отдельных узлах DOCKER или в подсистеме оркестрации контейнеров, например Kubernetes.

>[!div class="step-by-step"]
>[Назад](self-hosted.md)
>[Вперед](kubernetes.md)
