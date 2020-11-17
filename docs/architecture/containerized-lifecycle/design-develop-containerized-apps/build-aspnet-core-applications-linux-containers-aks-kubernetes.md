---
title: Сборка приложений ASP.NET Core, развернутых как контейнеры Linux в кластерах AKS/Kubernetes
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.date: 08/06/2020
ms.openlocfilehash: 831d2372131e20788d0f48190eb8c600aa02485c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440833"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Сборка приложений ASP.NET Core, развернутых как контейнеры Linux в оркестраторе AKS/Kubernetes

Служба Azure Kubernetes (AKS) представляет собой службы оркестрации управляемой среды Kubernetes в Azure, упрощающие развертывание контейнеров и управление ими.

Основные функции AKS:

- Размещенный в Azure уровень управления
- Автоматические обновления
- самовосстановление;
- Настраиваемое пользователем масштабирование
- Упрощение взаимодействия с пользователем для разработчиков и операторов кластера.

В приведенных ниже примерах рассматривается создание приложения ASP.NET Core 3.1, которое выполняется в Linux и развертывается в кластере AKS в Azure, при этом его разработка осуществляется в Visual Studio 2019.

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a>Создание проекта ASP.NET Core с помощью Visual Studio 2019

ASP.NET Core — это универсальная платформа разработки, которая поддерживается корпорацией Майкрософт и сообществом .NET на сайте GitHub. Она является кроссплатформенной, поддерживает Windows, Mac OS и Linux и может использоваться на устройствах, в облаке, во внедренных системах и в сценариях Интернета вещей.

В этом примере используется пара простых проектов, основанных на шаблонах Visual Studio, поэтому не требуется много дополнительных знаний для создания примера. Вам достаточно создать проект с помощью стандартного шаблона, который включает в себя все элементы для запуска небольшого проекта с помощью REST API и веб-приложение с Razor Pages, использующее технологии ASP.NET Core 3.1.

![Добавьте окно нового проекта в Visual Studio, выбрав "Веб-приложение ASP.NET Core".](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

**Рис. 4-35**. Создание веб-приложения ASP.NET Core в Visual Studio 2019.

Чтобы создать пример проекта в Visual Studio, выберите **Файл** > **Создать** > **Проект**, укажите тип проекта **Интернет** и затем выберите шаблон **Веб-приложение ASP.NET Core**. При необходимости можно также выполнить поиск шаблона.

Затем введите имя и расположение приложения, как показано на следующем рисунке.

![Введите имя и расположение проекта.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

**Рис. 4-36**. Введите имя и расположение проекта в Visual Studio 2019.

Убедитесь, что выбрана платформа ASP.NET Core 3.1. Платформа .NET Core 3.1 включена в последнюю версию продукта Visual Studio 2019 и автоматически устанавливается и настраивается при его установке.

![Диалоговое окно Visual Studio для выбора типа веб-приложения ASP.NET Core с выбранным параметром API.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

**Рис. 4-37**. Выбор ASP.NET Core 3.1 и типа проекта "Веб-API"

Обратите внимание, что поддержка Docker в настоящее время не включена. Отобразить ее можно после создания проекта.

При наличии любой предыдущей версии .NET Core можно скачать и установить версию 3.1 по адресу <https://dotnet.microsoft.com/download>.

Чтобы показать, что вы можете реализовать поддержку Docker в проекте в любое время, добавьте поддержку Docker сейчас. Щелкните узел проекта правой кнопкой мыши в обозревателе решений и выберите в контекстном меню пункт **Добавить** > **Поддержка Docker**.

![Пункт контекстного меню, позволяющий добавить поддержку Docker в существующий проект: Щелкните проект правой кнопкой мыши и выберите "Добавить" > "Поддержка Docker".](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

**Рис. 4-38**. Добавление поддержки Docker в существующий проект

Чтобы завершить добавление поддержки Docker, можно выбрать платформу Windows или Linux. В данном случае это **Linux**.

![Параметр диалогового окна для выбора целевой операционной системы для Dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

**Рис. 4-39**. Выбор контейнеров Linux.

Выполнив эти простые шаги, вы запустите свое приложение ASP.NET Core 3.1 в контейнере Linux.

Аналогичным образом можно добавить очень простой проект **WebApp** (рис. 4-40) для использования конечной точки веб-API, хотя здесь это не рассматривается.

После этого вы добавите поддержку оркестратора для проекта **WebApi**, как показано далее на рисунке 4-40.

![Добавление поддержки оркестратора в проект WebApi](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

**Рис. 4-40**. Добавление поддержки оркестратора в проект *WebApi*.

При выборе параметра `Docker Compose`, который подходит для локальной разработки, Visual Studio добавляет проект docker-compose с файлами docker-compose, как показано на рисунке 4-41.

![Добавление в решение docker-compose](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

**Рис. 4-41**. Добавление поддержки оркестратора в проект *WebApi*.

Эти исходные файлы похожи на следующие:

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

Чтобы приложение выполнялось с Docker Compose, необходимо внести несколько изменений в `docker-compose.override.yml`

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

Теперь приложение можно запустить с помощью клавиши **F5** или кнопки **Воспроизвести** либо сочетания клавиш **CTRL + F5**, выбрав проект docker-compose, как показано на рисунке 4-42.

![Выполнение проекта docker-compose с помощью Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

**Рис. 4-42**. Добавление поддержки оркестратора в проект *WebApi*.

При выполнении приложения docker-compose, как описано ниже, вы получаете следующее:

1. Созданные образы и контейнеры создаются в соответствии с файлом docker-compose.
2. В браузере открывается адрес, настроенный в диалоговом окне "Свойства" для проекта `docker-compose`.
3. Открывается окно **Контейнер** (в Visual Studio 2019 версии 16.4 и более поздней).
4. Предоставляется поддержка отладчика для всех проектов в решении, как показано на следующих изображениях.

Браузер открыт:

![Представление браузера с выполняющимся веб-приложением](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

**Рис. 4-43**. Окно браузера с приложением, выполняющимся в нескольких контейнерах.

Окно "Контейнеры"

![Окно "Контейнеры" в Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

**Рис. 4-44**. Окно "Контейнеры" в Visual Studio

Окно **Контейнеры** позволяет просматривать запущенные контейнеры, доступные образы, переменные среды, журналы и сопоставления портов, проверять файловую систему, подключать отладчик или открывать окно терминала в среде контейнера.

Как видно, интеграция между Visual Studio 2019 и Docker полностью ориентирована на обеспечение продуктивной работы разработчика.

Конечно, можно также вывести список образов с помощью команды `docker images`. Вы должны увидеть образы `webapi` и `webapp` с тегами `dev`, созданные при автоматическом развертывании вашего проекта с помощью Visual Studio 2019.

```console
docker images
```

![Выходные данные команды docker images в консоли представляют собой список, содержащий следующее: репозиторий, тег, идентификатор образа, дата создания и размер.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

**Рис. 4-45**. Представление образов Docker

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a>Регистрация решения в Реестре контейнеров Azure (ACR)

Вы можете отправить образы в [Реестр контейнеров Azure (ACR)](https://azure.microsoft.com/services/container-registry/), но можно также использовать Docker Hub или любой другой реестр, чтобы оттуда образы можно было развернуть в кластере AKS.

### <a name="create-an-acr-instance"></a>Создание экземпляра ACR

Выполните следующую команду из **az cli**:

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> Имя реестра контейнеров (например, `exploredocker`) должно быть уникальным в пределах Azure и содержать от 5 до 50 буквенно-цифровых знаков. Дополнительные сведения см. в разделе [Создание реестра контейнеров](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry).

### <a name="create-the-image-in-release-mode"></a>Создание образа в режиме выпуска

Теперь мы создадим образ в режиме **Выпуск** (готовом к выпуску), заменив значение на **Выпуск**, как показано на рис. 4-46, и запустив приложение, как и раньше.

![Параметр панели инструментов в Visual Studio для сборки в режиме выпуска.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

**Рис. 4-46**. Выбор режима выпуска

При выполнении команды `docker images` вы увидите создание обоих образов — одного для режима `debug` (**dev**) и другого для режима `release` (**latest**).

### <a name="create-a-new-tag-for-the-image"></a>Создание тега образа

Каждый образ контейнера должен быть помечен именем `loginServer` реестра. Данный тег используется для маршрутизации при отправке образов контейнеров в реестр образов.

Вы можете просмотреть имя `loginServer` на портале Azure, используя сведения из Реестра контейнеров Azure.

![Представление имени Реестра контейнеров Azure в правом верхнем углу браузера.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

**Рис. 4-47**. Представление имени реестра

Кроме того, можно выполнить следующую команду:

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Выходные данные консоли для указанной выше команды.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

**Рис. 4-48**. Получение имени реестра с помощью **az cli**

В обоих случаях вы получите нужное имя. В нашем примере это `exploredocker.azurecr.io`.

Теперь вы можете пометить образ, используя самый последний образ (образ выпуска), с помощью команды:

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

После выполнения команды `docker tag` выведите список образов с помощью команды `docker images`, при этом вы должны увидеть образ с новым тегом.

![Выходные данные команды docker images в консоли.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

**Рис. 4-49**. Представление помеченных образов

### <a name="push-the-image-into-the-azure-acr"></a>Отправка образа в Azure ACR

Войдите в Реестр контейнеров Azure:

```console
az acr login --name exploredocker
```

Отправьте образ в Реестр контейнеров Azure с помощью следующей команды:

```console
docker push <login-server-name>/<image-name>:v1
```

Этой команде требуется некоторое время на отправку образа, при этом она предоставляет вам сведения о выполняемой операции. На следующем рисунке видно, что выходные данные одного изображения готовы, а другие еще выполняются.

![Выходные данные команды docker push в консоли.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

**Рис. 4-50**. Выходные данные консоли для команды push.

Чтобы развернуть многоконтейнерное приложение в кластере AKS, потребуется несколько файлов манифеста, `.yaml` файлы, которые имеют большую часть свойств, взятых из файлов `docker-compose.yml` и `docker-compose.override.yml`.

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> Предыдущие файлы `.yml` включают только порты `HTTP` с помощью параметра `ASPNETCORE_URLS`, чтобы избежать проблем с отсутствующим сертификатом в примере приложения.

> [!TIP]
> Сведения о том, как создать кластер AKS для этого примера, см. в разделе [**Развертывание в службе Azure Kubernetes (AKS)**](deploy-azure-kubernetes-service.md) этого руководства.

Теперь почти все готово для развертывания с помощью **kubectl**, но сначала нужно получить учетные данные из кластера AKS с помощью следующей команды:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Выходные данные указанной выше команды в консоли: Объединено "explore-docker-aks" в качестве текущего контекста в C:\Users\Miguel.kube\config](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

**Рис. 4-51**. Получение учетных данных из AKS в среду kubectl.

Также необходимо разрешить кластеру AKS получать образы из ACR с помощью следующей команды:

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

Выполнение предыдущей команды может занять несколько минут. Затем используйте команду `kubectl apply` для запуска развертываний, а затем — `kubectl get all` для получения списка объектов кластера.

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Выходные данные консоли для указанной выше команды: развертывания применены. Службы созданы.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

**Рис. 4-52**. Развертывание в Kubernetes

Подождите некоторое время, пока подсистема балансировки нагрузки не получит внешний IP-адрес, проверив `kubectl get services`, после чего приложение должно быть доступно по этому адресу, как показано на следующем рисунке:

![Представление приложения, развернутого в AKS, в браузере](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

**Рис. 4-53**. Развертывание в Kubernetes

После завершения развертывания можно получить доступ к [веб-интерфейсу Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) с помощью локального прокси-сервера, используя туннель SSH.

Сначала необходимо создать ClusterRoleBinding с помощью следующей команды:

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

Чтобы запустить прокси-сервер, используйте следующую команду:

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

Окно браузера должно открыться в `http://127.0.0.1:8001` с представлением, аналогичным следующему:

![Представление панели мониторинга Kubernetes в браузере, показывающее развертывания, объекты pod, наборы реплик и службы.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

**Рис. 4-54**. Просмотр сведений о кластере Kubernetes

Теперь у вас есть приложение ASP.NET Core, которое выполняется в контейнерах Linux и развернуто в кластере AKS в Azure.

> [!NOTE]
> Дополнительные сведения о развертывании с использованием Kubernetes см. в статье <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

> [!div class="step-by-step"]
> [Назад](set-up-windows-containers-with-powershell.md)
> [Вперед](../docker-devops-workflow/index.md)
