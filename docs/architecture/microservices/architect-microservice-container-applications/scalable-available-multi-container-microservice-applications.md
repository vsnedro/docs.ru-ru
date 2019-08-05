---
title: Управление микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности
description: Описание вариантов управления микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности и возможностей Azure Dev Spaces при разработке жизненного цикла приложений Kubernetes.
ms.date: 09/20/2018
ms.openlocfilehash: 76fa68cee41f8d1f34ec399c346f457efae57151
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675031"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Управление микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности

Использование оркестраторов для приложений, готовых к развертыванию в рабочей среде, крайне важно, если приложение основано на микрослужбах или просто разнесено по нескольким контейнерам. Как было сказано ранее, в рамках подхода на основе микрослужб каждая микрослужба имеет собственную модель и данные, поэтому она является автономной с точки зрения разработки и развертывания. Но если у вас есть более традиционное бизнес-приложение, состоящее из нескольких служб (например, SOA) и требующее распределенного развертывания, оно также будет включать в себя несколько контейнеров или служб. Такие системы сложны в масштабировании и управлении, поэтому для создания масштабируемого многоконтейнерного приложения, готового к развертыванию в рабочей среде, оркестратор абсолютно необходим.

На рис. 4-23 показано развертывание приложения, состоящего из нескольких микрослужб (контейнеров) в кластере.

![Составные приложения Docker в кластере: для каждого экземпляра службы используется один контейнер. Контейнеры Docker являются "единицами развертывания", а отдельный контейнер является экземпляром Docker. Узел обрабатывает много контейнеров.](./media/image23.png)

**Рис. 4-23**. Кластер контейнеров

Такой подход выглядит логичным. Однако как обеспечить балансировку нагрузки, маршрутизацию и оркестрацию для таких составных приложений?

Обычная подсистема Docker в узлах Docker позволяет управлять экземплярами образов в отдельных узлах, но ее недостаточно, если требуется управлять множеством контейнеров, развернутых в нескольких узлах, в рамках более сложного распределенного приложения. В большинстве случаев необходима платформа управления, которая будет автоматически запускать контейнеры, масштабировать контейнеры с несколькими экземплярами в каждом образе, а также при необходимости приостанавливать или завершать их работу. В идеале она также должна контролировать доступ к ресурсам, таким как сеть и хранилище данных.

Чтобы перейти от управления отдельными контейнерами или очень простыми составными приложениями к управлению крупными корпоративными приложениями с микрослужбами, следует прибегнуть к платформам оркестрации и кластеризации.

С точки зрения архитектуры и разработки, если вы создаете крупные корпоративные приложения на основе микрослужб, важно знать следующие платформы и продукты, которые поддерживают сложные сценарии:

**Кластеры и оркестраторы**. Если вам нужно масштабировать приложения на множестве узлов Docker, как в случае с крупным приложением на основе микрослужб, крайне важно иметь возможность управлять всеми этими узлами как единым кластером, абстрагируясь от сложности базовой платформы. Именно такую возможность предоставляют кластеры контейнеров и оркестраторы. Примером оркестратора может служить Kubernetes. Функции Kubernetes доступны в Azure через Службу Azure Kubernetes.

**Планировщики**. *Планировщик* дает администратору возможность запускать контейнеры в кластере посредством пользовательского интерфейса. Планировщик кластера имеет несколько функций: обеспечение эффективного использования ресурсов в кластере, применение заданных пользователем ограничений, эффективная балансировка нагрузки контейнеров между узлами, а также обеспечение устойчивости к ошибкам и высокой доступности.

Понятия кластера и планировщика тесно связаны друг с другом, поэтому продукты, предоставляемые разными поставщиками, часто включают в себя оба набора возможностей. Ниже приведен список наиболее важных платформ и программного обеспечения, предоставляющих возможности управления кластерами и планирования. Эти оркестраторы, как правило, предлагаются в составе публичных облачных платформ, таких как Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Программные платформы для кластеризации контейнеров, оркестрации и планирования

### <a name="kubernetes"></a>Kubernetes

![Логотип Kubernetes](./media/image24.png)

> [*Kubernetes*](https://kubernetes.io/) — это решение с открытым кодом, которое предоставляет широкий ряд возможностей: от организации инфраструктуры кластера и планирования контейнеров до оркестрации. Оно позволяет автоматизировать развертывание, масштабирование и выполнение операций с контейнерами приложений в кластерах узлов.
>
> *Kubernetes* предоставляет ориентированную на контейнеры инфраструктуру, которая объединяет контейнеры приложений в логические блоки, чтобы упростить управление и обнаружение.
>
> Решение *Kubernetes* является зрелым в Linux и менее зрелым в Windows.

### <a name="azure-kubernetes-service-aks"></a>Служба Azure Kubernetes (AKS)

![Логотип службы Azure Kubernetes](./media/image41.png)

> [Служба Azure Kubernetes (AKS)](https://azure.microsoft.com/services/kubernetes-service/) является управляемой службой оркестрации контейнеров Kubernetes в Azure, которая упрощает управление, развертывание и эксплуатацию кластера Kubernetes.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Использование оркестраторов на основе контейнеров в Microsoft Azure

Ряд поставщиков облачных служб, включая Microsoft Azure, Amazon EC2 Container Service и Google Container Engine, предлагают поддержку контейнеров Docker, а также кластеров Docker и оркестрации. Microsoft Azure поддерживает кластер и оркестратор Docker посредством службы Azure Kubernetes (AKS).

## <a name="using-azure-kubernetes-service"></a>Использование службы Azure Kubernetes

Кластер Kubernetes объединяет несколько узлов Docker в пул и предоставляет доступ к ним как к единому виртуальному узлу Docker, что позволяет развертывать несколько узлов в кластере и осуществлять масштабирование, добавляя любое число экземпляров контейнеров. Кластер отвечает за выполнение всех сложных задач управления, включая масштабирование, обеспечение работоспособности и т. д.

Служба AKS позволяет упростить создание и настройку кластера виртуальных машин в Azure, предварительно настроенных для выполнения упакованных в контейнеры приложений, а также управление им. Благодаря оптимизированной конфигурации популярных средств планирования и оркестрации с открытым кодом служба AKS дает возможность развертывать приложения на основе контейнеров в Microsoft Azure и управлять ими, используя имеющиеся навыки или прибегая к знаниям большого и продолжающего расширяться сообщества.

Служба Azure Kubernetes оптимизирует настройку популярных средств и технологий кластеризации Docker с открытым кодом для Azure. Вы получаете открытое решение, которое обеспечивает переносимость как контейнеров, так и конфигурации приложения. Вы выбираете размер, число узлов и средства оркестрации, а служба Azure Kubernetes делает все остальное.

![Структура кластера Kubernetes: один главный узел, который обрабатывает DNS, планировщик, прокси-сервер и т. д., и несколько рабочих узлов, на которых размещены контейнеры.](media/image36.png)

**Рис. 4-24**. Упрощенная структура и топология кластера Kubernetes

На рис. 4-24 показана структура кластера Kubernetes, где главный узел (виртуальная машина) управляет большинством операций по координации кластера, и вы можете развертывать контейнеры на остальных узлах (управляемых как единый пул с точки зрения приложения). Это позволяет расширять среду до тысяч и даже десятков тысяч контейнеров.

## <a name="development-environment-for-kubernetes"></a>Среда разработки для Kubernetes

Что касается среды разработки, [в июле 2018 г. компания Docker объявила](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/), что Kubernetes также можно запускать на одном компьютере разработки (Windows 10 или macOS), просто установив [Docker Desktop](https://docs.docker.com/install/). Позднее можно развернуть ее в облаке (AKS) для дальнейшего тестирования интеграции, как показано на рис. 4-25.

![В июле 2018 г. компания Docker объявила о поддержке компьютера разработки для кластеров Kubernetes с помощью Docker Desktop.](media/image37.png) 

**Рис. 4-25**. Выполнение Kubernetes на компьютере разработки и в облаке

## <a name="getting-started-with-azure-kubernetes-service-aks"></a>Начало работы со службой Azure Kubernetes (AKS) 

Чтобы начать использовать AKS, необходимо развернуть кластер AKS с помощью портала Azure или интерфейса командной строки. Подробные сведения о развертывании кластера Kubernetes в Azure см. в статье [Краткое руководство. Развертывание кластера Службы Azure Kubernetes (AKS) с помощью портала Azure](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

За программное обеспечение, устанавливаемое по умолчанию в составе службы AKS, плата не взимается. Все возможности по умолчанию реализуются с помощью ПО с открытым кодом. Служба AKS доступна для нескольких виртуальных машин в Azure. Плата взимается только за выбранные вычислительные операции, а также за другие используемые ресурсы базовой инфраструктуры, такие как хранилище и сеть. За саму службу AKS вы дополнительно не платите.

Дополнительные сведения о реализации развертывания в Kubernetes на основе kubectl и исходных YAML-файлов см. в публикации [Setting eShopOnContainers up in AKS (Azure Kubernetes Service)](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.-Setting-the-solution-up-in-AKS-(Azure-Kubernetes-Service)) (Настройка eShopOnContainers в AKS (служба Azure Kubernetes)).

## <a name="deploying-with-helm-charts-into-kubernetes-clusters"></a>Развертывание с помощью чартов Helm в кластерах Kubernetes

При развертывании приложения в кластере Kubernetes можно использовать оригинальное средство CLI kubectl.exe, использующее файлы развертывания на основе собственного формата (YAML-файлы), как уже упоминалось в предыдущем разделе. Однако для более сложных приложений Kubernetes, например при развертывании сложных приложений на основе микрослужб, мы рекомендуем использовать [Helm](https://helm.sh/).

Чарты Helm помогают осуществлять определение, управление версиями, установку, предоставление общего доступа, обновление или откат даже самых сложных приложений Kubernetes.

Более того, использование Helm рекомендуется, поскольку дополнительные среды Kubernetes в Azure, такие как [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces), также основаны на чартах Helm.

Поддержка Helm осуществляется фондом [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) в сотрудничестве с корпорацией Майкрософт, Google, Bitnami и сообществом Helm.

Дополнительные сведения о реализации чартов Helm и Kubernetes см. в публикации [Using Helm Charts to deploy eShopOnContainers to AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Deploying-to-AKS-using-Helm-Charts) (Использование чартов Helm для развертывания eShopOnContainers в AKS).

## <a name="use-azure-dev-spaces-for-your-kubernetes-application-lifecycle"></a>Использование Azure Dev Spaces в жизненном цикле приложения Kubernetes

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) обеспечивает быструю итеративную среду разработки Kubernetes для команд разработчиков. Выполнив минимальную настройку компьютера разработки, можно итеративно запускать и отлаживать контейнеры непосредственно в службе Azure Kubernetes (AKS). Для разработки приложений Windows, Mac или Linux вы можете использовать привычные инструменты, такие как Visual Studio, Visual Studio Code или командная строка.

Как уже упоминалось, Azure Dev Spaces используют чарты Helm при развертывании контейнерных приложений.

Azure Dev Spaces помогает командам разработчиков работать более производительно в Kubernetes, так как позволяет быстро выполнять итерацию и отладку кода непосредственно в глобальном кластере Kubernetes в Azure просто с помощью Visual Studio 2017 или Visual Studio Code. Кластер Kubernetes в Azure — это общий управляемый кластер Kubernetes, поэтому ваша команда может работать совместно. Вы можете разрабатывать код в изолированном пространстве, а затем развернуть его в глобальном кластере и выполнить сквозное тестирование с другими компонентами без репликации или имитации зависимостей.

Как показано на рис. 4-26, наиболее характерная функция Azure Dev Spaces — возможность создания "пространств", которые могут выполняться, будучи интегрированными с остальной частью глобального развертывания в кластере.

![Azure Dev Spaces позволяет прозрачно комбинировать и сопоставлять рабочие микрослужбы с экземпляром контейнера разработки, упрощая тестирование новых версий.](media/image38.png)

**Рис. 4-26**. Использование нескольких пространств в Azure Dev Spaces

По сути, вы можете настроить общее пространство разработки в Azure. Каждый разработчик может сосредоточиться на своей части приложения и последовательно разрабатывать код до фиксации в пространстве разработки, которое уже содержит все остальные службы и облачные ресурсы, от которых зависят их сценарии. Зависимости всегда находятся в актуальном состоянии, и разработчики работают в среде, отражающей рабочую.

Azure Dev Spaces обеспечивает отдельное пространство, позволяющее работать относительно изолированно, без риска помешать другим членам команды. Каждое пространство разработки является частью иерархической структуры, которая позволяет переопределить одну (или несколько) микрослужбу из главного пространства разработки с помощью своей разрабатываемой микрослужбы.

Эта возможность основана на префиксах URL-адресов, поэтому при использовании какого-либо префикса пространства разработки в URL-адресе запрос обрабатывается в целевой микрослужбе, если она существует в области разработки. В противном случае он перенаправляется до первого экземпляра целевой микрослужбы в иерархии, в конечном итоге добираясь до главного пространства разработки наверху.

Вы можете ознакомиться с [вики-страницей eShopOnContainers в Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Using-Azure-Dev-Spaces-and-AKS), чтобы получить представление о практическом применении функции на конкретном примере.

Дополнительные сведения см. в статье [Коллективная разработка с помощью Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Начало работы со службой Azure Kubernetes (AKS)**  \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Azure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes** (официальный сайт). \
  <https://kubernetes.io/>

>[!div class="step-by-step"]
>[Назад](resilient-high-availability-microservices.md)
>[Вперед](../docker-application-development-process/index.md)