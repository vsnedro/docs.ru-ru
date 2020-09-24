---
title: Другие параметры развертывания контейнера
description: Другие варианты развертывания контейнеров с помощью Azure
ms.date: 05/13/2020
ms.openlocfilehash: 2eac822b74af636e0ab0ed24b58eb7139526f4a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163626"
---
# <a name="other-container-deployment-options"></a>Другие параметры развертывания контейнера

Помимо службы Azure Kubernetes (AKS) можно также развернуть контейнеры в службе приложений Azure для контейнеров и экземпляров контейнеров Azure.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>Когда имеет смысл выполнить развертывание в службе приложений для контейнеров?

Простые рабочие приложения, которые не нуждаются в согласовании, хорошо подходят для службы приложений Azure для контейнеров.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Развертывание в службе приложений для контейнеров

Для развертывания в [службе приложений Azure для контейнеров](https://azure.microsoft.com/services/app-service/containers/)вам потребуется экземпляр реестра контейнеров Azure (запись контроля доступа) и учетные данные для доступа к нему. Отправьте образ контейнера в репозиторий записей контроля доступа, чтобы он мог быть извлечен в службу приложений Azure. После завершения можно настроить приложение для непрерывного развертывания. Это позволит автоматически развертывать обновления при каждом изменении изображения в записи контроля доступа.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Когда имеет смысл выполнить развертывание в службе "экземпляры контейнеров Azure"?

Служба ["экземпляры контейнеров Azure" (ACI)](https://azure.microsoft.com/services/container-instances/) позволяет запускать контейнеры DOCKER в управляемой безсерверной облачной среде без необходимости настраивать виртуальные машины или кластеры. Это отличное решение для кратковременных рабочих нагрузок, которые могут выполняться в изолированном контейнере. Рассмотрим ACI для простых служб, сценариев тестирования, автоматизации задач и заданий сборки. ACI развертывает экземпляр контейнера, выполняет задачу, а затем выворачивает ее.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Развертывание приложения в службе "экземпляры контейнеров Azure"

Для развертывания в [службе "экземпляры контейнеров Azure" (ACI)](/azure/container-instances/)вам потребуется реестр контейнеров Azure (запись контроля доступа) и учетные данные для обращения к ней. После отправки образа контейнера в репозиторий он доступен для ACI. Вы можете работать с ACI, используя портал Azure или интерфейс командной строки. Запись контроля доступа обеспечивает тесную интеграцию с ACI. На рис. 3-14 показано, как отправить индивидуальный образ контейнера в запись контроля доступа.

![Экземпляр запуска реестра контейнеров Azure](./media/acr-runinstance-contextmenu.png)

**Рис. 3-14**. Экземпляр запуска реестра контейнеров Azure

Создание экземпляра в ACI может быть выполнено быстро. Укажите реестр образа, сведения о группе ресурсов Azure, объем выделяемой памяти и порт для прослушивания. В этом [кратком руководстве показано, как развернуть экземпляр контейнера в ACI с помощью портал Azure](/azure/container-instances/container-instances-quickstart-portal).

После завершения развертывания найдите только что развернутый IP-адрес контейнера и взаимодействует с ним через указанный порт.

Служба "экземпляры контейнеров Azure" предлагает самый быстрый способ выполнения простых рабочих нагрузок контейнера в Azure. Вам не нужно настраивать службу приложений, Orchestrator или виртуальную машину. Для сценариев, в которых требуется полное согласование контейнеров, обнаружение служб, автоматическое масштабирование или координированные обновления, мы рекомендуем использовать службу Kubernetes Azure (AKS).

## <a name="references"></a>Ссылки

- [Что такое Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Установка Kubernetes с помощью Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube VS DOCKER Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Инструменты Visual Studio для Docker](/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [Общие сведения о бессерверном холодном запуске](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Предварительно подготовленные экземпляры функций Azure](/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Создание функции в Linux из пользовательского образа](/azure/azure-functions/functions-create-function-linux-custom-image)
- [Запуск функций Azure в контейнере DOCKER](https://markheath.net/post/azure-functions-docker)
- [Создание функции в Linux из пользовательского образа](/azure/azure-functions/functions-create-function-linux-custom-image)
- [Функции Azure с автомасштабированием, управляемым событиями Kubernetes](/azure/azure-functions/functions-kubernetes-keda)
- [Выпуск ранний](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces с VS Code](/azure/dev-spaces/quickstart-netcore)
- [Azure Dev Spaces с помощью Visual Studio](/azure/dev-spaces/quickstart-netcore-visualstudio)
- [AKS нескольких пулов узлов](/azure/aks/use-multiple-node-pools)
- [Автомасштабирование кластера AKS](/azure/aks/cluster-autoscaler)
- [Руководство. масштабирование приложений в AKS](/azure/aks/tutorial-kubernetes-scale)
- [Масштабирование и размещение Функций Azure](/azure/azure-functions/functions-scale)
- [Документация по службе "экземпляры контейнеров Azure"](/azure/container-instances/)
- [Развертывание экземпляра контейнера из записи контроля доступа](/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Назад](scale-containers-serverless.md)
>[Вперед](communication-patterns.md)
