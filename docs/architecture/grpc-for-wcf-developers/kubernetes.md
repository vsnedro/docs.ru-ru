---
title: Kubernetes-gRPC для разработчиков WCF
description: Запуск ASP.NET Core gRPC Services в кластере Kubernetes.
ms.date: 12/15/2020
ms.openlocfilehash: 0b457d6fa982b5f5b983194d4aedbff0eb782f36
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938067"
---
# <a name="kubernetes"></a>Kubernetes

Хотя контейнеры можно запускать вручную на узлах DOCKER, для надежных рабочих систем лучше использовать механизм оркестрации контейнеров для управления несколькими экземплярами, работающими на нескольких серверах в кластере. Доступны различные механизмы оркестрации контейнеров, в том числе Kubernetes, Docker Swarm и Apache Mesos. Но из этих ядер Kubernetes далеко и далеко не самый широко используемый, поэтому он будет посвящен этой главе.

Kubernetes включает следующие функциональные возможности:

- **Планирование** запускает контейнеры на нескольких узлах в кластере, обеспечивая сбалансированное использование доступного ресурса, поддержание работоспособности контейнеров при сбоях и обработку последовательных обновлений для новых версий образов или новых конфигураций.
- **Проверки работоспособности** отслеживают контейнеры, чтобы обеспечить непрерывную работу службы.
- **Обнаружение службы DNS &** обрабатывает маршрутизацию между службами в кластере.
- Входящий трафик **предоставляет доступ к** выбранным службам извне и обычно обеспечивает балансировку нагрузки между экземплярами этих служб.
- **Управление ресурсами** подключает внешние ресурсы, например хранилище, к контейнерам.

В этой главе подробно описано, как развернуть службу ASP.NET Core gRPC и веб-сайт, который использует эту службу в кластере Kubernetes. Пример используемого приложения доступен в репозитории [DotNet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.

## <a name="kubernetes-terminology"></a>Терминология Kubernetes

Kubernetes использует *конфигурацию требуемого состояния*. API используется для *описания таких объектов*, как модули Pod, *развертывания* и *службы*, и *плоскость управления* требует реализации требуемого состояния на всех *узлах* *кластера*. В кластере Kubernetes имеется *главный* узел, на котором работает *API Kubernetes*, который можно взаимодействовать программно или с помощью `kubectl` программы командной строки. `kubectl` может создавать объекты и управлять ими с помощью аргументов командной строки, но лучше подходит для файлов YAML, содержащих данные объявления для объектов Kubernetes.

### <a name="kubernetes-yaml-files"></a>Файлы YAML Kubernetes

Каждый файл YAML Kubernetes будет иметь по крайней мере три свойства верхнего уровня:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

`apiVersion`Свойство используется для указания версии (и API), для которой предназначен файл. `kind`Свойство определяет тип объекта, представляемого YAML. `metadata`Свойство содержит такие свойства объектов `name` , как, `namespace` и `labels` .

В большинстве файлов YAML Kubernetes также есть `spec` раздел, описывающий ресурсы и конфигурацию, необходимые для создания объекта.

### <a name="pods"></a>Модули pod

Модули Pod являются основными единицами выполнения в Kubernetes. Они могут запускать несколько контейнеров, но они также используются для выполнения отдельных контейнеров. Модуль также включает все ресурсы хранилища, необходимые контейнерам, и сетевой IP-адрес.

### <a name="services"></a>Службы

Службы являются мета-объектами, описывающими Pod (или наборы модулей), и предоставляют способ доступа к ним в кластере, например для сопоставления имени службы с набором IP-адресов Pod с помощью службы DNS кластера.

### <a name="deployments"></a>Развернутые приложения

Развертывания — это объекты *требуемого состояния* для модулей Pod. Если вы создаете модуль Pod вручную, он не будет перезапущен после завершения его работы. Развертывания используются для информирования кластера о том, какие модули, и сколько реплик этих модулей следует запускать в настоящее время.

### <a name="other-objects"></a>Другие объекты

Модули Pod, службы и развертывания — это всего три основных типа объектов. Существуют десятки других типов объектов, управляемых кластерами Kubernetes. Дополнительные сведения см. в документации по [основным понятиям Kubernetes](https://kubernetes.io/docs/concepts/) .

### <a name="namespaces"></a>Пространства имен

Кластеры Kubernetes предназначены для масштабирования до сотен или тысяч узлов и для запуска аналогичного числа служб. Чтобы избежать конфликта между именами объектов, пространства имен используются для группирования объектов вместе в составе более крупных приложений. Собственные службы Kubernetes выполняются в `default` пространстве имен. Все объекты пользователя должны создаваться в собственных пространствах имен, чтобы избежать возможных конфликт с объектами по умолчанию или другими клиентами в кластере.

## <a name="get-started-with-kubernetes"></a>Начало работы с Kubernetes

Если вы используете DOCKER Desktop для Windows или DOCKER Desktop для Mac, Kubernetes уже доступен. Просто включите его в разделе **Kubernetes** окна **Параметры** :

![Включение Kubernetes в DOCKER Desktop](media/kubernetes/enable-kubernetes-docker-desktop-v2.png)

Чтобы запустить локальный кластер Kubernetes в Linux, рассмотрите возможность [minikube](https://github.com/kubernetes/minikube)или [MicroK8s](https://microk8s.io/) , если дистрибутив Linux поддерживает [привязку](https://snapcraft.io/).

Чтобы убедиться, что кластер работает и доступен, выполните `kubectl version` команду:

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:50:19Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:41:49Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"linux/amd64"}
```

В этом примере как CLI, так `kubectl` и сервер Kubernetes работают под управлением версии 1.14.6. Каждая версия должна `kubectl` поддерживать предыдущую и следующую версии сервера, поэтому `kubectl` 1,14 должна работать с серверными версиями 1,13 и 1,15.

## <a name="run-services-on-kubernetes"></a>Запуск служб на Kubernetes

Пример приложения содержит `kube` каталог, содержащий три файла YAML. `namespace.yml`Файл объявляет пользовательское пространство имен: `stocks` . `stockdata.yml`Файл объявляет развертывание и службу для приложения gRPC, а `stockweb.yml` файл объявляет развертывание и службу для веб-приложения ASP.NET Core 5,0 MVC, которое использует службу gRPC.

Чтобы использовать `YAML` файл с `kubectl` , выполните `apply -f` команду:

```console
kubectl apply -f object.yml
```

`apply`Команда проверит допустимость файла YAML и отобразит все ошибки, полученные от API, но не ждет, пока все объекты, объявленные в файле, не будут созданы, так как этот шаг может занять некоторое время. Используйте `kubectl get` команду с соответствующими типами объектов для проверки создания объекта в кластере.

### <a name="the-namespace-declaration"></a>Объявление пространства имен

Объявление пространства имен является простым и требует только присваивания `name` :

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

Используйте `kubectl` , чтобы применить `namespace.yml` файл и убедиться, что пространство имен успешно создано:

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a>Приложение Стоккдата

В `stockdata.yml` файле объявляются два объекта: развертывание и служба.

#### <a name="the-stockdata-deployment"></a>Развертывание Стоккдата

Часть развертывания файла YAML предоставляет `spec` для самого развертывания, включая необходимое количество реплик, а также `template` для создания объектов Pod и управления ими при развертывании. Обратите внимание, что объекты развертывания управляются `apps` API, как указано в `apiVersion` , а не в основном API Kubernetes.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 1
  template:
    metadata:
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

`spec.selector`Свойство используется для сопоставления выполняющихся модулей Pod с развертыванием. `metadata.labels`Свойство Pod должно соответствовать `matchLabels` свойству, иначе вызов API завершится ошибкой.

В `template.spec` разделе объявляется контейнер для выполнения. При работе с локальным кластером Kubernetes, например, предоставленным с помощью DOCKER Desktop, можно указать образы, которые были собраны локально, если у них есть тег версии.

> [!IMPORTANT]
> По умолчанию Kubernetes всегда проверяет и пытается извлечь новый образ. Если образ не удается найти ни в одном из известных репозиториев, создание Pod завершится ошибкой. Для работы с локальными образами задайте для параметра значение `imagePullPolicy` `Never` .

`ports`Свойство указывает, какие порты контейнера должны быть опубликованы в модуле Pod. `stockservice`Образ запускает службу на стандартном HTTP-порте, поэтому порт 80 публикуется.

`resources`Раздел применяет ограничения ресурсов к контейнеру, выполняющемуся в модуле Pod. Это хороший подход, так как он предотвращает использование всеми доступными ЦП или памяти на узле отдельным модулем.

> [!NOTE]
> ASP.NET Core 5,0 оптимизирована и настроена для работы в контейнерах с ограниченными ресурсами. `dotnet/core/aspnet`Образ DOCKER задает переменную среды, чтобы указать `dotnet` среде выполнения, что она находится в контейнере.

#### <a name="the-stockdata-service"></a>Служба Стоккдата

Часть службы файла YAML объявляет службу, которая предоставляет доступ к модулям Pod в кластере.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

Служба `spec` использует `selector` свойство для сопоставления с выполнением `Pods` , в данном случае поиск модулей Pod с меткой `run: stockdata` . Указанный параметр `port` в соответствующих модулях Pod публикуется с помощью именованной службы. Другие модули, выполняющиеся в `stocks` пространстве имен, могут обращаться к HTTP через эту службу, используя в `http://stockdata` качестве адреса. Для модулей Pod, выполняющихся в других пространствах имен, можно использовать `http://stockdata.stocks` имя узла. Управлять доступом к службам между пространствами имен можно с помощью [политик сети](https://kubernetes.io/docs/concepts/services-networking/network-policies/).

#### <a name="deploy-the-stockdata-application"></a>Развертывание приложения Стоккдата

Используйте `kubectl` , чтобы применить `stockdata.yml` файл и убедиться, что развертывание и служба созданы:

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a>Приложение Стокквеб

`stockweb.yml`Файл объявляет развертывание и службу для приложения MVC.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a>Переменные среды

В `env` разделе объекта развертывания указываются переменные среды, которые должны быть заданы в контейнере, где выполняются `stockweb:1.0.0` образы.

**`StockData__Address`** Переменная среды будет сопоставлена с `StockData:Address` параметром конфигурации благодаря поставщику конфигурации EnvironmentVariables. Этот параметр использует двойные подчеркивания между именами, чтобы разделить разделы. Адрес использует имя службы `stockdata` службы, которое выполняется в том же пространстве имен Kubernetes.

**`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** Переменная среды задает <xref:System.AppContext> параметр, который включает незашифрованные соединения HTTP/2 для <xref:System.Net.Http.HttpClient> . Эта переменная среды выполняет те же действия, что и установка переключателя в коде, как показано ниже:

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Если для параметра используется переменная среды, контекст можно легко изменить в зависимости от контекста, в котором выполняется приложение.

#### <a name="service-types"></a>Типы услуг

`type: NodePort`Свойство используется, чтобы сделать веб-приложение доступным извне кластера. Этот тип свойства приводит к тому, что Kubernetes публикует порт 80 в службе на произвольный порт в внешних сетевых сокетах кластера. Назначенный порт можно найти с помощью `kubectl get service` команды.

`stockdata`Служба не должна быть доступна извне кластера, поэтому она использует тип по умолчанию, `ClusterIP` .

В рабочих системах, скорее всего, будет использоваться интегрированная подсистема балансировки нагрузки для предоставления доступа к общедоступным приложениям внешним потребителям. Службы, предоставляемые таким образом, должны использовать `LoadBalancer` тип.

Дополнительные сведения о типах служб см. в документации по [службам Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .

#### <a name="deploy-the-stockweb-application"></a>Развертывание приложения Стокквеб

Используйте `kubectl` , чтобы применить `stockweb.yml` файл и убедиться, что развертывание и служба созданы:

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

Выходные данные `get service` команды показывают, что HTTP-порт был опубликован для порта `32564` внешней сети. Для приложения DOCKER Desktop этот IP-адрес будет иметь значение localhost. Доступ к приложению можно получить, перейдя по адресу `http://localhost:32564` .

### <a name="test-the-application"></a>Тестирование приложения

В приложении Стокквеб отображается список акций НАСДАК, полученных из простой службы "запрос-ответ". В этой демонстрации каждая строка также показывает уникальный идентификатор экземпляра службы, который его вернул.

![Снимок экрана Стокквеб](media/kubernetes/stockweb-screenshot.png)

Если количество реплик `stockdata` службы увеличилось, можно ожидать, что значение **сервера** изменится с line на Line, но на самом деле все записи 100 всегда возвращаются из одного и того же экземпляра. Если страница обновляется каждые несколько секунд, идентификатор сервера остается прежним. Почему это происходит? Здесь можно воспроизвести два фактора.

Во-первых, система обнаружения службы Kubernetes по умолчанию использует балансировку нагрузки с циклическим перебором. При первом запросе DNS-сервера он вернет первый соответствующий IP-адрес для службы. В следующий раз он вернет следующий IP-адрес в списке и т. д. до конца. На этом этапе он вернется к началу.

Во-вторых, объект, `HttpClient` используемый для клиента gRPC приложения стокквеб, создается и управляется [ASP.NET Core хттпклиентфактори](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), а один экземпляр этого клиента используется для каждого вызова страницы. Клиент выполняет только один поиск DNS, поэтому все запросы направляются на один и тот же IP-адрес. И поскольку `HttpClientHandler` кэшируется в целях повышения производительности, несколько запросов в быстром выполнении будут  использовать один и тот же IP-адрес, пока не истечет кэшированный DNS-элемент или не будет удален экземпляр обработчика по некоторой причине.

В результате запросы по умолчанию к службе gRPC не сбалансированы по всем экземплярам этой службы в кластере. Разные потребители будут использовать разные экземпляры, но это не гарантирует хорошее распределение запросов или сбалансированное использование ресурсов.

Следующая глава, « [сети службы](service-mesh.md)», будет решать эту проблему.

>[!div class="step-by-step"]
>[Назад](docker.md)
>[Вперед](service-mesh.md)
